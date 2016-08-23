#! /usr/bin/env ruby

require 'fileutils'
require 'json'
require 'yaml'

def dir_blacklist
  ["css", "js", "images", "script"]
end

def useless?(f)
  f.start_with?("_") ||
    f.start_with?(".") ||
    !File.directory?(f) ||
    dir_blacklist.include?(f)
end

def get_gif_dirs
  Dir.foreach(".").map { |f| f unless useless?(f) }.compact
end

def liquid_info_for_file(path)
  # Get all the tags from the path, but without the extension
  tags = path.gsub('-', File::SEPARATOR).gsub('_', File::SEPARATOR).gsub('.', File::SEPARATOR).split(File::SEPARATOR)[0 .. -1]
  tags.uniq!
  tags.sort!

  {
    "title"         => File.basename(path),
    "category"      => path.split(File::SEPARATOR)[0],
    "path"          => path,
    "modified_time" => File.mtime(path).to_i,
    "tags"          => tags
  }
end

dirs  = get_gif_dirs
files = []

dirs.each do |dir|
  Dir.glob("#{dir}/**/*.{gif,jpg,jpeg,png}") do |gif|
    files << liquid_info_for_file(gif)
  end
end

# Sort the files
files.sort! { |a,b| a[:path] <=> b[:path] }

FileUtils.mkdir_p("_data") unless File.directory?("_data")
FileUtils.mkdir_p("_includes") unless File.directory?("_includes")
File.open("_data/static_files.yml", 'w') { |f| f.write(YAML.dump(files)) }
File.open("_includes/site-index.json", 'w') { |f| f.write(JSON.dump(files)) }
