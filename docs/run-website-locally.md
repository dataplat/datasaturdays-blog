To run the website locally follow instructions in Robs blog https://blog.robsewell.com

`docker run --volume="$PWD:/srv/jekyll"   -p 4001:4000 jekyll/jekyll:3.8.6 jekyll serve --force-polling`

CTRL C

`docker ps -a`

`XY2` is the first 3 characters of the container

`docker commit XY2`  

`docker run --rm --volume="$PWD:/srv/jekyll"   -p 4001:4000 dsblog jekyll serve --force-polling`

Website is at 

http://localhost:4001/datasaturdays-blog/

