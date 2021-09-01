# Get information from YouTube

## Video

Using name:

```js
const Nightcord = require('nightcord');
const YouTube = new Nightcord.YouTube();

YouTube.getVideo("Alan Walker Faded").then(video => {
    console.log(video.title)
});
```

Output:
```
Alan Walker - Faded
```

Using Links:

```js
YouTube.getVideo("https://www.youtube.com/watch?v=60ItHLz5WEA").then(video => {
    console.log(video.title)
});
```

Output:
```
Alan Walker - Faded
```

`video` has the following properties:

```js
{
    title: "Video title",
    url: "Video Link",
    id: "Video Link ID",
    thumbnail: "Video Thumbnail Link",
    duration: {
        seconds: "Total seconds of in the video",
        timestamp: "Total Duration/timestamp in video (example: 5:24)"
    },
    author: {
        name: "The video's owner name",
        channelURL: "The channel link of this video."
    }
}
```

## Playlist (using ID only)

Using ID:

```js
const Nightcord = require('Nightcord');
const YouTube = new Nightcord.YouTube();

YouTube.getPlaylist("PLRBp0Fe2GpgmbpTy0fNGpoEtEzcDJ1IgQ").then(list => {
    list.videos.forEach(video => console.log(video.title))
});
```

Output:

```
Unknown Brain - Faceless (ft. Marvin Divine & Bri Tolani) [NCS Lyrics]
Unknown Brain - Jungle of Love (ft. Glaceo) [NCS Lyrics]
Unknown Brain - Candy (ft. Linn Sandin) [NCS Lyrics]
Unknown Brain - Blackhole (ft. Ava King) [NCS Lyrics]
Unknown Brain - Blackhole (ft. Ava King) [NCS Lyrics]
Unknown Brain - DEAD (ft. KAZHI) [NCS Lyrics]
Unknown Brain - Oh Darling [NCS Lyrics]
Unknown Brain - Dancing On The Moon ft. Luke Burr [NCS Lyrics]
Unknown Brain - Hollywood Perfect (ft. NotEvenTanner) [NCS Lyrics]
Unknown Brain - Forget You (ft. Shiah Maisel) [NCS Lyrics]
Unknown Brain - Dance With Me (ft. Alexis Donn) [NCS Lyrics]
Unknown Brain - Let You Go (ft. NotEvenTanner) [NCS Lyrics]
Unknown Brain & Kyle Reynolds - I'm Sorry Mom [NCS Lyrics]
Unknown Brain - Childhood Dreams [NCS Lyrics]
Unknown Brain - Don't Bother (ft. Emily J) [NCS Lyrics]
Unknown Brain - Last Thing (ft. Charlotte Sands) [NCS Lyrics]
Unknown Brain & Hoober - Phenomenon (ft. Dax & VinDon) [NCS Lyrics]
```

`list` has the following properties:

```js
{
    title: "Playlist Title",
    id: "Playlist ID",
    url: "Playlist Link",
    videosCount: "Amount of videos in this playlist",
    viewCount: "Amount of views altogether from the videos in this playlist",
    createdDate: "Date of when the playlist was created",
    videos: "Display all videos on this playlist and information in JSON.",
    thumbnail: "Playlist Thumbnail Link",
    author: {
        name: "Playlist's channel name",
        channelURL: "Playlist's channel URL"
    }
}
```
