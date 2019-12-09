ziroom.com api for node

### Usage

```ts
import * as ziroom from "ziroom";

(async function() {
  const QianMenRooms = await ziroom.getAllRoomsByArea(
    "116.423679",
    "116.475421",
    "39.906717",
    "39.929599"
  );
  console.log("there are " + QianMenRooms.length + " rooms");
})();
```

### API Reference

#### getRoomsByArea(minLng, maxLng, minLat, maxLat, page=1, zoom=16)

Get all rooms in a rectangular area, which defined by longitude and latitude. You can pick coordinate parameters with [this tool](https://api.map.baidu.com/lbsapi/getpoint/index.html). With the `pages` and `total` returned, you could manage pagination manually.

#### getAllRoomsByArea(minLng, maxLng, minLat, maxLat, zoom=16)

This is a wrapper for `getRoomsByArea` which manage pagination automatically, so it returns all rooms in the area.

#### getAllResBlocksByArea(minLng, maxLng, minLat, maxLat, zoom=16)

Get all `ResBlock`s in a rectangular area. `ResBlock` usually represents a community.

#### getRoomsByResBlock(resBlockID, page=1)

Get all rooms in a `ResBlock`. You could manage pagination manually.

#### getAllRoomsByResBlock(resBlockID)

Wrapper for `getRoomsByResBlock` with pagination automatically managed.

#### [WIP] getRoomDetail(roomID)

Returns a JSON object, which contains as much information as we can get from webpage.

#### [WIP] getRoomSnapshot(roomID)

Generate a static HTML page to display room detail.

