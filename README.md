# gif storage

Storage place for all my favorite gifs.

![thumbs up](thumbs-up/thumbs-up.gif)

## Contributing

Feel free to open a pull request if you have a gif that you really think belongs in here. However, I will only accept images that I think I will personally want to use.

I'm not trying to build a comprehensive storage place for the world's best gifs, just trying to organize all the gifs I personally use. I sync these locally, so I'll be somewhat selective about adding new stuff. That said, feel free to suggest ones you think are awesome, and if I don't accept the PR just fork the repo and add to your own! :thumbsup:

## Curating your own gif library

You can also [fork](https://github.com/jglovier/gifs/fork) this repository to your own account, and have your own gif library. Once you fork to your own account, you can even host your own GH Pages site ([like mine](http://gifs.joelglovier.com/)) by editing or removing the [CNAME](https://github.com/jglovier/gifs/blob/gh-pages/CNAME) file in your fork accordingly.

To update the site index on the GH Pages site, you'll need to run the index build script. Just clone the project to your local machine, open Terminal, and `cd` into the repo. Then, run `script/build_site_index` and commit your changes. Once the new index is commited to your gh-pages branch, it will be live on your site as soon as the CDN updates (usually within a few minutes).

## Troubleshooting
- If your build is failing in Travis, try deleting the `Gemfile.lock` and rebuilding it by running `bundle install` and then `bundle update`
- If gifs aren't showing up on your hosted version, check to make sure that you rebuilt the site index (`script/build_site_index`)

## Gifwit support

Thanks to [@orderedlist](http://github.com/orderedlist), you can quickly access all the gifs in my repo via the handy OSX app [Gifwit](http://gifwit.com/). Just download the [library.gifwit](http://gifs.joelglovier.com/library.gifwit ) file and open in Gifwit. Gifwit will import all the gifs from the repo and you'll be able to easily access the production URLs via keyboard shortcuts. :zap:
