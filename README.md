<!--# quec-app-advance-map-->

## 地图组件

### 一、组件功能列表

|功能    |功能说明    |实现版本    |微服务版本号|
| --- | --- | --- | --- |
|地图相关    | 地图展示、覆盖物、地理逆编码、POI搜索 |    1.0.0    | |

### 二、设计接口/属性

### MapConfig 方法

|Methed|    Description|    Result|
| --- | --- | --- |
|setMapType(number)|    设置地图类型：1，百度地图；2，谷歌地图    |
|initGoogleSearchPosition|    初始化Google地图搜索    ||

### MapView 属性

|Prop    |Type    |是否必填    |Description| Remarks |
|  ----  | ----  |  ----  | ----  | ----  |
|zoomControlsVisible    |bool|    否    |显示放大缩小按钮，默认 false|仅支持百度地图 |
|isTrafficEnabled|    bool    | 否    |显示交通路线，默认 false | |
|isBaiduHeatMapEnabled    |bool    |否    |显示百度热力图层，默认 false| 仅支持百度地图 |
|type    |number    |否    |地图类型 1: 标准地图 2: 卫星地图 3:空白地图，默认标准地图| |
|locationEnabled    |bool    |否    |显示当前定位位置，默认 false | |
|myLocationData    |object|    否    |显示当前定位数据, 使用该属性前locationEnabled必须设置为true|
|zoom|    number|    否    |百度地图缩放级别[4,21]，谷歌地图缩放级别是[0, 20]| |
|zoomMinLevel |number|    否    |地图最小缩放级别| |
|zoomMaxLevel    |number|    否    |地图最大缩放级别| |
|centerLatLng|    object    |否    |地图中心点位置{latitude: ..., longitude: ...}| |
|zoomGesturesEnabled|    true    |否|    是否允许缩放手势，默认 true | |
|scrollGesturesEnabled    |bool|    否|    是否允许拖拽手势，默认 true | |
|overlookingGesturesEnabled|    bool|    否|    是否允许俯视手势，默认 true | 仅支持百度地图|
|rotateGesturesEnabled    |bool    |否    |是否允许旋转手势， 默认 true | |
|mapCustomStyleFileName    |string    |否    |用于设置个性化地图的样式文件| |
|onMapLoaded    |func|    否    |地图加载完成回调| |
|onMapClick    |func    |否|    点击地图回调| |
|onMapPoiClick    |func    |否|    点击地图地点回调| |
|onMapLongClick    |func|    否    |长按地图回调| |
|onMapDoubleClick    |func|    否|    双击地图回调|仅支持百度地图 |
|onMapStatusChangeStart|    func|    否|    地图状态开始变化回调|仅支持百度地图 |
|onMapStatusChange    |func|    否    |地图状态变化中回调|仅支持百度地图 |
|onMapStatusChangeFinish|    func    |否    |地图状态变化结束回调| 仅支持百度地图|
|onMarkerClick    |func|    否|    点击marker回调| |
|onMarkerDragStart|    func|    否    |拖拽marker开始回调| |
|onMarkerDrag    |func    |否|    拖拽marker中回调| |
|onMarkerDragEnd|    func    |否|    拖拽marker结束回调| |

### MapView 方法

|Methed|    Description|    Result|
| --- | --- | --- |
|setCenter({latitude, longitude})|    设置地图中心点位置    |
|setZoom(number)    |设置地图缩放    |
|setZoomToSpanMarkers( [{latitude, longitude}])    |地图中所有的marker点显示在视图内    |

### Marker 属性

|Prop|    Type    |是否必填    |Description|Remarks|
| --- | --- | --- | --- |---|
|title    |string    |否    |infowindow内容||
|location    |object    | 否    |坐标，{latitude, longitude}||
|icon    |any    |    否|Marker图片，支持本地与远程||
|draggable    |bool    |否    |是否可拖拽，默认 false ||
|active|    bool|    否    |是否显示infowind，默认 false ||
|infoWindowYOffset|    number    |否    |infowind y轴偏移,正数向下移动，负数向上移动，默认 false ||
|scale    |number    |否    |icon缩放大小,默认 1| 仅android，仅支持百度地图|
|perspective    |bool    |否|    是否开启近大远小效果, 默认 false |仅android，仅支持百度地图|
|alpha    |number    |否    |透明度, 默认 0|仅android|
|rotate    |number    |否    |旋转角度,默认 0|仅android|
|flat    |bool    |否    |是否平贴地图, 默认 false |仅android|
|infoWindowMinHeight|    number    |否    |infoWindow 最小高度, 默认 100 |仅android，仅支持百度地图|
|infoWindowMinWidth    |number    |否    |infoWindow 最小宽度, 仅android，默认 200 |仅android，仅支持百度地图|
|infoWindowTextSize    |number    |否    |infoWindow 字体, 默认 16|仅android，仅支持百度地图|

### Polyline 属性

|Prop    |Type    |是否必填    |Description|
| --- | --- | --- | --- |
|points    |LatLang[]    |是    |折线坐标点列表,[{latitude, longitude}]|
|color    |string|    否|    线条颜色，需要完整的rrggbb类型， 如：#000000|
|width    |number    |否    |线条宽度|

### Arc 属性(仅支持百度地图)

|Prop    |Type    |是否必填    |Description|
| --- | --- | --- | --- |
|points    |LatLang[]    |是    |折线坐标点列表,[{latitude, longitude}]|
|color    |string|    否|    线条颜色，需要完整的rrggbb类型， 如：#000000|
|width    |number    |否    |线条宽度|

### Circle 属性

|Prop    |Type    |是否必填    |Description|Remarks|
| --- | --- | --- | --- |---|
|circleCenter    |LatLang    | 是    |圆形中点||
|color    |string    |否    |边框颜色，需要完整的rrggbb类型， 如：#000000||
|width    |number    |否    |边框宽度||
|radius|    number    |是    |圆形半径||
|fillColor    |string|    否    |圆形背景颜色，android可使用十六进制控制透明度， ios使用fillColorAlpha属性||
|fillColorAlpha    |number|    否    |圆形背景颜色透明度|仅ios|

### Polygon 属性

|Prop    |Type    |是否必填    |Description|Remarks|
| --- | --- | --- | --- |---|
|points    |LatLang[]    |是    |多边形坐标点列表||
|color    |string    |否    |边框颜色，需要完整的rrggbb类型， 如：#000000|
|width    |number    |否    |边框宽度||
|fillColor    |string|    否    |圆形背景颜色，android可使用十六进制控制透明度， ios使用fillColorAlpha属性|
|fillColorAlpha    |number|    否    |圆形背景颜色透明度|仅ios|

### Geolocation 方法

|Method|Description|Remarks|
| --- | --- | --- | 
|  start () |    开始持续定位     ||
| stop()     | 停止持续定位     ||
|addListener(func)     |定位成功监听     |geolocation result |
| geocode(address, city) :Promise | 地理编码方法 |仅支持百度地图|
| reverseGeoCode(lat, lng) :Promise | 逆地理编码方法 ||

### Search 方法

### POI检索（仅支持百度地图）

|Method    |Description    |Result|
| --- | --- | --- |
|searchInCity(city, keyword, pageNum): Promise|    POI城市内检索（关键字检索）    |search result
|searchNearby({latitude, longitude, keyword, pageNum, radius}): Promise    |周边检索 geolocation result|

### 地点检索

<table>
<thead>
<tr>
<th>Method</th><th>Description</th><th>Result</th><th>Remarks</th>
</tr>
</thead>
<tbody>
<tr>
<td>requestSuggestion(city, keyword): Promise</td><td> 输入提示检索</td><td>search result</td><td>百度地图返回结果：<code>
{
    code:1000,
    type:1,
    poiList:[
        {
            name:"111",
            address:"",
            city:"",
            province:"",
            uid:"",
            latitude:39.935,
            longitude:116.404844
        }
    ]
}
</code>

google地图返回结果：<code>{ code:1000, type:1, poiList:[
{ name:"111", address:"", uid:"", }
]
}
</code>
</td>
</tr>
<tr>
<td>getGooglePoiDetail(uid): Promise</td><td>获取Google地点详情</td><td>poi detail</td><td>
google地点详情结果：
<code>
{
name:"111",
address:"",
uid:"",
latitude:39.935,
longitude:116.404844
}
</code>
</td>
</tr>
</tbody>
</table>

## 三、使用步骤

### 安装

```
$ yarn add quec-app-advanced-map

```

### 配置

### 如果你使用的react native的版本>=0.60.0,则无需做多余配置，只需要配置相关地图申请的key。

### Android配置：

```
<application>
    //百度地图配置
    <meta-data
        android:name="com.baidu.lbsapi.API_KEY"
        android:value="你的key" />
    //Google地图配置
    <meta-data
        android:name="com.google.android.geo.API_KEY"
        android:value="Google地图key"/>
    //Google Places SDK for Android 配置
    <meta-data
        android:name="com.google.android.place.API_KEY"
        android:value="Google Place Key"/>
</application>
```

### iOS配置：

### 注：ios更新版本需要删除之前导入的引用代码，重新导入新版本才会生效。

### 第一步： 在Podfile文件中加入以下代码：

```
  pod 'BaiduMapKit', '5.1.0'  百度地图
  pod 'BMKLocationKit', '1.8.0' 百度定位
  pod 'GoogleMaps', '5.1.0'    谷歌地图
  pod 'GooglePlaces', '5.0.0'  谷歌搜索
```

### 第二步： 在运行命令

```
cd ios && pod install

```

### 第三步： 等待安装成功后，进入ios工程文件夹，会看到一个.xcworkspace 结尾的文件 ，双击打开

![RUNOOB 图标](photo_1.png)

### 点击找到本项目node_modules下的quec-app-advanced-map -> ios -> RNSMapClasses, 将整个RNSMapClasses文件夹导入。

![RUNOOB 图标](photo_2.png)

### 第四步： 在MapAPIKey.h文件中配置地图相关的key

```
static NSString * const BaiduMapKey = @"r9dis1O1xqNQqDYiGhRIHdiRDhvH5TeK";
static NSString * const BaiduMapLocationKey = @"r9dis1O1xqNQqDYiGhRIHdiRDhvH5TeK";
static NSString * const GoogleMapKey = @"AIzaSyB0-bnqVoZNc-vrDyS3_AdtDPp6gwOZw_o";
static NSString * const GoogleMapPlaceKey = @"AIzaSyB0-bnqVoZNc-vrDyS3_AdtDPp6gwOZw_o";

```

### 到此配置结束。

### 具体API用法可以参考[demo](http://192.168.23.184:8108/frontend/app/business/quec-app-business-baidu-map-demo)。

## 四、依赖

### Android 依赖

```
    // google 依赖
    implementation 'com.google.android.gms:play-services-maps:17.0.1'
    implementation 'com.google.android.libraries.places:places:2.4.0'
    implementation 'com.google.android.gms:play-services-location:18.0.0'
    //百度地图
    libBaiduMapSDK_base_v7_3_0.so
    libBaiduMapSDK_map_v7_3_0.so
    libgnustl_shared.so
    libindoor.so
    liblocSDK8a.so
```
