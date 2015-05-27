# Youku-parse
an angular directive for parsing youku video id into real urls.

# Last Update
Last update the algorithm on March 23rd.
Functional test on May 27th, worked well.
Added the cross domain support using jsonp.

# Source
All the parse functions are from [http://runjs.cn/code/incos4te](http://runjs.cn/code/incos4te).

I just did the wrapping for angular.

# How the cross domain works?
Since the Youku website itself doesn't support "jsonp" (a type of cross domain data fetch). A personal server did the job of grasping youku json files at the backend, opening a usable jsonp api for use.

# Usage
* Inject the module

        angular.module('YourModule','windht.youku')
    
* Use the service!

        angular.controller('YourCtrl',[Youku,function(Youku){
          Youku.getVideoSrc(anyVideoID).then(function(url){
              // Maybe directly use this url to load a video! No ads!
              angular.element('ChooseAPlayer!').attr('src',url);
          });
        }])
        
* Or directly and simply use a nice directive
        
        <video youku-id="XOTY1MjQ2OTc2"></video>

* And there you go!

# Updating
In case of any change of the parsing functions, this service will update in a periodically of one months. Post any issues for hurry update.
