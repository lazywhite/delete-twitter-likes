## How to use

1. Sign in to Twitter in Firefox or a Chromium browser
2. Go to your Profile
3. Go the Likes section
4. Open DevTools and go to the 'Console' tab
5. Copy and paste the following script

```
setInterval(function(){
var divs = document.getElementsByTagName('div')
var arr = Array.prototype.slice.call(divs)
var hearts = arr.filter(x => x.getAttribute('data-testid') == 'unlike')
hearts.forEach(h => h.click())
window.scrollTo(0, document.body.scrollHeight ||document.documentElement.scrollHeight);
},1000);
```

## FAQs

### Twitter says I still have likes

Twitter may show you have any number of likes even if the likes tab says **You don’t have any likes yet**. It can take days, months, or years for older tweets to reappear in that tab, so just be patient and wait for them to come back.

### The script doesn't work!

Twitter is [rate limited to 900 requests every 15 minutes](https://developer.twitter.com/en/docs/twitter-api/rate-limits), so you will start getting an error after 900 requests. Refresh the page to pause the script, then resubmit the script after 15 minutes.

If you find any other bugs, please submit an issue or pull request for a fix.

## Thanks

I grabbed this from a comment on [this article](https://www.techjunkie.com/delete-all-twitter-likes/#comment-47485) and fixed it to work with a copy-and-paste from browser. This repo is for me to remember it easily.
