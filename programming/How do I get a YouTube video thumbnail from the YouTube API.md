# How do I get a YouTube video thumbnail from the YouTube API?

Each YouTube video has four generated images. They are predictably formatted as follows:

```PY
https://img.youtube.com/vi/<insert-youtube-video-id-here>/0.jpg
https://img.youtube.com/vi/<insert-youtube-video-id-here>/1.jpg
https://img.youtube.com/vi/<insert-youtube-video-id-here>/2.jpg
https://img.youtube.com/vi/<insert-youtube-video-id-here>/3.jpg
```

The first one in the list is a full size image and others are thumbnail images. The default thumbnail image (i.e., one of `1.jpg`, `2.jpg`, `3.jpg`) is:

```md
https://img.youtube.com/vi/<insert-youtube-video-id-here>/default.jpg
```

For the high quality version of the thumbnail use a URL similar to this:

```python
https://img.youtube.com/vi/<insert-youtube-video-id-here>/hqdefault.jpg
```

There is also a medium quality version of the thumbnail, using a URL similar to the HQ:

```java
https://img.youtube.com/vi/<insert-youtube-video-id-here>/mqdefault.jpg
```

For the standard definition version of the thumbnail, use a URL similar to this:

```javascript
https://img.youtube.com/vi/<insert-youtube-video-id-here>/sddefault.jpg
```

For the maximum resolution version of the thumbnail use a URL similar to this:

```c++
https://img.youtube.com/vi/<insert-youtube-video-id-here>/maxresdefault.jpg
```

All of the above URLs are available over HTTP too. Additionally, the slightly shorter hostname `i3.ytimg.com` works in place of `img.youtube.com` in the example URLs above.

Alternatively, you can use the [YouTube Data API (v3)](https://developers.google.com/youtube/v3/) to get thumbnail images.
