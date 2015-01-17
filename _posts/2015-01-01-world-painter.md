---
title: World Painter
permalink: /world-painter
---

World Painter was a short term project that I worked on just before summer break ended in 2011. I saw [Engadget’s report of the contest](http://www.engadget.com/2011/07/31/microsoft-crowns-20-winners-in-mango-app-contest-losers-go-home/) on Twitter, and I figured that I would at least give it a try, especially since Canadians were actually eligible for once. Even more, although my school wasn’t technically eligible for DreamSpark, the people at Microsoft were very helpful in getting me a subscription for a year to participate in the contest.

After I set up the development environment, I spent about a day figuring out how to use Expression Studio Ultimate and the Windows Phone edition of Visual Studios. I’d also never seen a Windows Phone in real life before, so I spent some time looking up videos of how the apps were generally designed as well.

The entire prototype was made the next day (and most of the morning following). Since this was a prototype and not an actual app itself, I didn’t need to learn too much coding to get the basic interface going. Most of the work was actually done in Photoshop and on paper, then I fit the pieces into the app afterwards.

Here is the result:

<a href="{{ site.url }}/assets/embed/world_painter/Default.html">
<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/icon.png"/>
</a>

<p class="phone-screenshot-caption">Clicking this picture will take you to the Silverlight application that shows the prototype.</p>

<div class="row">

<div class="col-xm-6 col-sm-3 col-md-3">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/recent.png"/>

<p class="phone-screenshot-caption">Page 1 - recent</p>

</div>

<div class="col-xm-6 col-sm-3 col-md-3">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/paint.png"/>

<p class="phone-screenshot-caption">Page 2 - paint</p>

</div>

<div class="col-xm-6 col-sm-3 col-md-3">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/browse.png"/>

<p class="phone-screenshot-caption">Page 3 - browse</p>

</div>

<div class="col-xm-6 col-sm-3 col-md-3">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/settings.png"/>

<p class="phone-screenshot-caption">Page 4 - settings</p>

</div>

</div>

The first view seen when the app is first opened is the *recent* view. This view would show a feed of activities that related to your drawings. The main events that I thought would belong here were when someone on your friends list paints a picture, anyone likes your graffiti, or when someone paints over your graffiti. By default, all graffitis would be public, as that it the point of a graffiti, so all activities that related to your graffiti would appear here.

The next view is the *paint* view. This view shows your location and takes you directly to the painting view. I put this on the second page as I figured it would be reasonably easy to access, but I felt the recent activities should take higher priority than the creation aspect.

The third view lets you *browse* other people’s graffitis. I put a high priority on graffitis near the user’s location, as it would probably be the most interesting to see drawings in areas near you. That was also the reason for including an AR mode. The popular images section should motivate people to make better graffiti.

The last page was the *settings* page, as I figured most people would not access it very often, except for when setting up their “tag” – there signature on the bottom of a graffiti. Putting a setting as a page on a panorama view seems a little strange, but it seemed to be a common convention when I was exploring Windows Phone apps at the time.

<div class="row">

<div class="col-xm-6 col-sm-6">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/tag.png"/>

<p class="phone-screenshot-caption">Painting mode</p>

</div>

<div class="col-xm-6 col-sm-6">

<img class="phone-screenshot" src="{{ site.url }}/assets/img/world_painter/paint.png"/>

<p class="phone-screenshot-caption">AR mode</p>

</div>

</div>

Arguably the more interesting views are the drawing view and the AR view.

I would like to say that the drawing on the drawing view is intentionally terrible, as that looks like the most typical use case of the app. After all, the users would be drawing on their phone, and most people would not have the patience to sit there and spend a lot of time making it good. The important part to note about the view is that a picture will be taken and then the graffiti will go on top of the picture. This is important because…

The AR view shows a cloud in the distance that points to where a graffiti is. The picture is used as a preview, but the end goal was that if a person pointed a camera at the same place a person took a picture in AR mode, then that person would be able to see the graffiti overlaid on top of the image that the camera produced. I imagined people would be able to hold their smartphone up, especially at a city with a high population density, and see graffiti that other people left around the area.

Reasonably satisfied with what I had made, I submitted my entry on August 4th, and then…

<blockquote>
<p>Congrats to #WPAppItUp winners: @abhi235, @acromace, @apxapob, @baithxlol, @brilliantvision, @chriond, @dataq, @ddluk, @fahim_k</p>
<footer><a href="https://twitter.com/benlower/statuses/107164722188660736">Ben Lower (@benlower)</a></footer>
</blockquote>

I won! Not only that, it was one of the three that they picked as a favourite. I was ecstatic.

[You can click here to go to the Windows Phone Developer Blog where the winners were posted.](http://blogs.windows.com/windows_phone/b/wpdev/archive/2011/08/26/more-winners-for-wpappitup.aspx)

As of now, I cannot actually make the app a reality because of the incredible server space the service would require to store the pictures of any reasonable amount of users. More importantly, the core demographic that would use this app may not have a cellular data connection, which would severely limit the usability of the app. However, with more AR products on the horizon, especially products like Google Glass, I would expect to see an app similar to this to appear on the market. Perhaps when I get some capital, I will make it myself.
