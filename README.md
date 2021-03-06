# wallpaper_scans
This directory contains a simple script in Ruby that scans through the front-page of the wallpapers subreddit on reddit and downloads all of those in the 1st page. Places all pictures in a `/pics/{todays-date}/{url-dependent-name}` directory, with relative positioning to the script. The script supports imgur album downloads, and is capped at 15 pictures per album. This can be changed.
Can also work in theory for other subreddits that are mainly for user submitted pictures.
####Update 260116
Can now also download imgur albums nicely, places them in folders in the pics folder. 


# Use
The following instructions are for use and setup on windows.

RubyInstaller:
http://rubyinstaller.org/

Rails: http://railsinstaller.org/en

Installation of the nokogiri gem:
http://www.nokogiri.org/tutorials/installing_nokogiri.html#windows

Follow these steps to avoid an SSL error:
https://gist.github.com/fnichol/867550

As mentioned in the link, it's useful to set the environment variables for more than a 1-time use.
Go to Control Panel -> System & Security -> System -> Advanced System Settings -> Environment Variables -> New -> 
Name: SSL_CERT_FILE, Value = C:\RailsInstaller\cacert.pem

Once setup finished, just go to directory and call `ruby htmlScanner.rb {"optional-url"}` on the command line. Ensure the optional url is surrounded by speech marks `""`.
If this argument is not provided, the script defaults to downloading from the latest at [`/r/wallpapers`](https://www.reddit.com/r/wallpapers/). Alternatively, provide an optional url to attempt to download pictures from here.

This was my first real attempt at using Ruby on my own, and it's not the most elegant solution as of yet. Thanks to the Nokogiri gem for the help with HTML connections & for fNichol for the very useful link above.

### Untested ###
May work in other environments, see https://www.ruby-lang.org/en/downloads/ for UNIX based systems

#TODO:
1. ~~Setup https connections when downloading pictures too~~
2. ~~Nicer single imgur pic relocation link downloads~~
3. ~~Allow for nice downloads of imgur albums~~
4. GUI / Picture selector
5. Package into an .exe
6. Pass the script through the standards. (Rubocop?)
