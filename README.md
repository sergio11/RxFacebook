# RxFacebook

[![Join the chat at https://gitter.im/yongjhih/RxFacebook](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/yongjhih/RxFacebook?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![rxparse.png](art/rxfacebook.png)](art/rxfacebook.png)

<!--
[![rxfacebook.svg](art/rxfacebook.svg)](art/rxfacebook.svg)
-->

Facebook in RxJava.

## Usage

Login/Logout:

```java
FacebookObservable.login(activity).subscribe();
FacebookObservable.logout(activity).subscribe();
```

getPhotos:

```java
Observable<Photo> photos = FacebookObservable.getPhotos(activity);
// entity: Profile Album Event Page
Observable<Photo> photos = FacebookObservable.getPhotos(activity, entityId);

Observable<Photo> photo = FacebookObservable.getPhoto(activity, attachement);
```

getPosts:

```java
Observable<Post> posts = FacebookObservable.getPosts(activity);
// entity: Profile Event Group Page
Observable<Post> posts = FacebookObservable.getPosts(activity, entityId);
// status: links, statuses, posts or tagged
Observable<Post> posts = FacebookObservable.getPosts(activity, entityId, PostType.STATUSES);
```

getAttachment:

```java
Observable<Attachment> attachment = FacebookObservable.getAttachment(activity, post);
// entity: Post, ?
Observable<Attachment> attachment = FacebookObservable.getAttachment(activity, entityId);
```

getAccounts:

```java
Observable<Account> accounts = FacebookObservable.getAccounts(activity);
```

getAlbums:

```java
Observable<Album> albums = FacebookObservable.getAlbums(activity);
// entity: Profile Page
Observable<Album> albums = FacebookObservable.getAlbums(activity, entityId);

Observable<Album> album = FacebookObservable.getAlbum(activity, albumId);
```

getComments:

```java
// entity: Album Checkin Comment Photo Post Video
Observable<Comment> comments = FacebookObservable.getComments(activity, entityId);
Observable<Comment> comment = FacebookObservable.getComments(activity, commentId);
```

getEvents:

```java
Observable<Event> events = FacebookObservable.getEvents(activity, EventDecision.ATTENDING);
// entity: Profile, Page, Group
Observable<Event> events = FacebookObservable.getEvents(activity, entityId, EventDecision.ATTENDING);
```

getFamilyUsers:

```java
Observable<FamilyUser> familyUsers = FacebookObservable.getFamily(activity);
Observable<FamilyUser> familyUsers = FacebookObservable.getFamily(activity, profileId);
```

getFriends:

```java
Observable<Profile> friends = FacebookObservable.getFriends(activity);
```

getGroups:

```java
Observable<Group> groups = FacebookObservable.getGroups(activity);
// entity: Profile
Observable<Group> groups = FacebookObservable.getGroups(activity, entityId);
```

getLikes:

```java
// entity: Album Checkin Comment Photo Post Video
Observable<Like> likes = FacebookObservable.getLikes(activity, entityId);
```

* -Get requests-
* -Get books-
* -Get games-
* -Get movies-
* -Get music-
* -Get notifications-
* -Get objects-
* -Get page-
* -Get scores-
* -Get television-
* -Get videos-

## Installation

```gradle
repositories {
    maven {
        url "https://jitpack.io"
    }
}

dependencies {
    compile 'com.github.yongjhih:rxfacebook:1.0.0'
}
```

## Build

DIY:

```
$ git clone https://github.com/sromku/android-simple-facebook
$ cd RxFacebook
$ ./gradlew assembleDebug
```

## Credit

Based on sromku/android-simple-facebook.

* sromku

## TODO

* Backpressure more posts/photos/comments
* `.subscribeOn(AndroidSchedulers.mainThread())` issue

## LICENSE

Copyright 2015 8tory, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
