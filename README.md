[![Gitter](https://badges.gitter.im/nagracks/reddit_get_top_images.svg)](https://gitter.im/nagracks/reddit_get_top_images?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

# reddit_get_top_images

> `reddit_get_top_images` is a script that can be used to download
> all the top images from any subreddit of http://www.reddit.com.

> It can be adjusted to get images from any segment of time,
> like images from the last hour, day, or week etc.

> The script will create a folder in your $home directory
> called `reddit_pics`.

Usage
-----

**Here is a typical API usecase that will get all the top images**
**of www.reddit.com/r/getmotivated from last week.**
```
import get_top_images as gi

sub_reddit = 'getmotivated'
tir = gi.TopImageRetreiver(sub_reddit, limit=5)
for url in tir.get_top_submissions():
    _download_it(url, tir)
```

**Here is a typical CLI usecase that will do the same:**

`python get_top_images.py -s getmotivated -p w`

**Here are the full arguments for CLI use:**

```
usage: get_top_images.py [-h] [--subreddit SUBREDDIT] [--period {h,d,w,m,y,a}]
                         [--limit N] [--destination DST]

Download top pics from any subreddit

optional arguments:
  -h, --help            show this help message and exit
  --subreddit SUBREDDIT, -s SUBREDDIT
                        Name of the subreddit
  --period {h,d,w,m,y,a}, -p {h,d,w,m,y,a}
                        [h]our, [d]ay, [w]eek, [m]onth, [y]ear, or [a]ll.
                        Period of time from which you want images. Default to
                        'get_top_from_[w]eek'
  --limit N, -l N       Maximum URL limit. Default to 15
  --destination DST, -d DST
                        Destination path. By default it saves to
                        $HOME/reddit_pics
```

Contributing
------------

This project is intended as a beginner friendly collaborative code, and anyone that wants to add, extend or otherwise improve this code is free to do so. Even if they have never contributed to another repository before.

LICENSE
------

`reddit_get_top_images` is licensed under
[GPL3](LICENSE)
