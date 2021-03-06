# Rate Limiting

For requests using client keys, you can make up to 720 requests per hour. The rate limit for IP restricted keys can be negoitiated depending on the requirements of your application. If your application will be using client keys in production, bear in mind that the rate limit equates to 1 request every 5 seconds so consider caching frequently accessed data.

## Check my rate limit

The simplest way of checking the status of your rate limit is by logging in to [TC] World and viewing your rate limit status under 'My Account': [world.city-driving.co.uk/?page=myaccount](http://world.city-driving.co.uk/?page=myaccount)

You can also check the returned HTTP headers of API requests to see the status of your rate limit, for instance with `curl`:

```shell
$ curl -i "http://api.tc-gaming.co.uk/citydriving/stats/online?key=YOUR_KEY"
```

```shell
HTTP/1.1 200 OK
Date: Sat, 18 Mar 2017 08:27:06 GMT
X-RateLimit-Limit: 720/3600
X-RateLimit-Remaining: 588
X-RateLimit-Reset: 1489814179
```