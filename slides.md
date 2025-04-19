---
theme: the-unnamed
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: From Bare Metal to Abstraction
info: |
  ## From Bare Metal to Abstraction
  A There and Back Again Tale to the Heart of Cloud-Native Computing.

  Over the past 30 years we've seen a quick evolution from bare metal servers and infrastructure to a reliance on Cloud Native practices, principles, and services. But have you ever stopped to think about what it was like before you could just type aws ec2 run-instances --instance-type m2.xlarge or gcloud compute instances create to spin up a new server or service? And how things actually got done when you had to wait 6 months for a server?
  In this talk, Jeremy will walk through infrastructure's evolution from his time in the mid-90s as a SysAdmin at an Internet Provider and shadow IT in the 2000s, to the growth of ,today's cloud native world. He'll highlight the enduring importance of core operational principles and explore how lessons from the "dark ages" of IT, particularly regarding automation and standardization, remain vital in today's cloud-native world. You'll gain a crucial historical context of infrastructure evolution, transforming their understanding from "how" to use the cloud to "why" it works the way it does, hopefully making them better engineers, and also have a chuckle or two.
  https://bsky.app/profile/jerdog.dev/post/3lkiveaaavs24
conference: ""
socialimg: /img/bluesky-jerdog-white.png
# https://sli.dev/features/drawing
drawings:
  persist: false
defaults:
  layout: center
  transition: fade
#  class: text-center
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
addons:
  - slidev-component-progress
## Current slide
# apply unocss classes to the current slide
class:
  - text-center
  - my-cool-content-on-the-left
layout: image-right
image: /img/slides/legacy-land-default.webp
backgroundSize: contain
---

# From Bare Metal to Abstraction
## A There and Back Again Tale to the Heart of Cloud-Native Computing.

<!--
I did entertain the idea of coming out dressed as Gandalf or Bilbo Baggins, but thankfully only for a moment. And don't let my gray beard fool you - this is not going to entirely be a talk about the days of yesteryear. I promise to keep it relevant to today and the future. Plus I only have 20 minutes, so I can't go too far down the rabbit hole. But I do want to take you on a journey through time and space, from the dark ages of IT to the bright future of cloud-native computing. So buckle up, because we're about to embark on an adventure that will make even Bilbo Baggins proud.
-->

---
layout: two-cols
class: text-center
---

<span style="position: relative; top: 20%;">

  ## Jeremy Meiss{style="color: deepskyblue; background: none;"}

  <p style="font-weight: bold;">Director, DevEx & DevRel</p>
  <p class="text-sm italic">OneStream Software</p>
  <p style="font-weight: bold;">DevOpsDays KC Organizer</p>

</span>

::right::

![alt text](/img/profile-pic.jpg){style="position: relative; margin: auto; width: 80%; border-radius: 15px 50px; "}

<!--
First off, let's start with a little bit about me. My name is Jeremy Meiss, and I am the Director of Developer Experience and Developer Relations at OneStream Software. I also help organize DevOpsDays Kansas City.
-->

---




<!--

-->

---
layout: image
image: /img/slides/not-the-90s.png
backgroundSize: contain
---


<!--
Now I do take slight offense at this site and what they classify as "1990s data center photos"... I mean, we did have colour photos back then!
-->

---

![alt text](/img/slides/me-in-the-90s.jpg){style="resizing: contain; width: 60%; position: relative; margin: auto;"}


<!--
I mean look at me in the 90s! These were my graduation photos from high school. Not long after these photos were taken, I started working at an Internet Service Provider in Kansas City as Tech Support.
-->

---

![alt text](/img/slides/networking-equipment.jpg){style="resizing: contain; width: 60%; position: relative; margin: auto;"}

<!--
I eventually moved into the Network Operations Center, and became a SysAdmin and Network Admin and was installing ISDN around KC, using the original IOS (Cisco Internetwork OS) to program Cisco 2500s and 7000s. I even had a Cisco 7000 under my desk and a dedicated T1 - with 1.544 Mbps (megabits per second) transfer rates. Those were the days... Like all of us back then, we were learning on the job! I mean who didn't accidentally mess up internet routes and bring down portions of the internet with routing leaks and route flapping?
-->

---
layout: two-cols-header
class: text-center
layoutClass: gap-8
---

## BGP, the "Two Napkin Protocol"

::left::

![alt text](/img/slides/two-napkin-protocol-bgp-1.jpg){style="resizing: contain; width: 80%; position: relative; margin: auto;"}

::right::

![alt text](/img/slides/two-napkin-protocol-bgp-2.jpg){style="resizing: contain; width: 80%; position: relative; margin: auto;"}

<!--
Who all knows that BGP (border gateway protocol) was invented in 1989 here in Austin at an IETF meeting, on the back of some napkins? It was commonly referred to as the "two napkin protocol" because of that.
-->

---
layout: two-cols
layoutClass: gap-8
class: text-center
---

![alt text](/img/slides/cubicle_life.jpg){style="resizing: contain; top: 30%; width: 40%; position: absolute; margin: auto;"}

::right::

![alt text](/img/slides/cubicle_image.png){style="resizing: contain; top: 20%; width: 50%; position: absolute; margin: auto;"}

<!--
In the early 2000s I was at Sprint where I survived 11 years, and ended up being shadow IT for the Network Services department. I started automating and migrating intricate Excel spreadsheets and Access databases to ASP web applications with MySQL and had a whole server farm under my desk. By which I mean 3 Dell OptiPlex desktops fully upgraded running VMWare and VirtualBox. Couldn't find a good image, and only Claude could create one that came close to depicting my cubicle.
-->

---
layout: image
image: /img/slides/dwarves_server_room.jpg
---

<v-clicks>
  <v-click>&nbsp;</v-click>
  <v-click>&nbsp;</v-click>
  <v-click>&nbsp;</v-click>
</v-clicks>

<!--
Back then there was no such thing as "cloud computing" - it was all about bare metal servers and virtualization. [click]I mean, who remembers the days of having to physically rack and stack servers in a data center? Or the thrill of getting a new server and having to install everything from scratch? It was like Christmas morning, but with more sweat and tears. [click]And blood. Who else still has the scars from sharp server racks and the internals of servers, where evidently the engineers were not concerned about safety and didn't think to dull the steel edges? [click]The amount of DNA that can be found in servers will keep future archaeologists busy for years trying to figure out when we created cyborgs.
-->

---
layout: image
image: /img/slides/ordering-a-server.jpg
backgroundSize: contain
---

<v-clicks>
  <v-click>&nbsp;</v-click>
  <v-click>&nbsp;</v-click>
  <v-click>&nbsp;</v-click>
</v-clicks>

<!--
The process to get a server was a long and arduous one. You had to go to Dell's website, customize what you wanted, and then send it over to IT fulfillment, wait for your manager to approve, then wait for the hardware to be ordered, and then shipped - a process that took a few months. [click]Meanwhile you had to submit an IT ticket to let them know a server was being shipped to a specific data center and that you needed space, and then they would eventually assign a rack, [click]and then you would have to submit a different ticket to a different team to schedule a time for you to come into the data center to set it up. [click]And if you were lucky, you might get a server within a month or two. But if you were really unlucky, you might have to wait six months or more. And that was before you had to install and configure everything.
-->

---
layout: image
image: /img/slides/no-tech-support.jpg
backgroundSize: contain
---


<!--
And that was just building servers in the late 90s and early 2000s. Think about all of the other things we had to do back then. We had to manually configure just about everything, from the network settings to the operating system. And if something went wrong, well, good luck trying to figure out what it was because online docs and support systems weren't available. We didn't have the luxury of cloud providers and their fancy dashboards and APIs. There was no ClickOps. We had to rely on our own wits and a lot of trial and error.
-->

---

## The Dark Ages of IT

- No online documentation
- Power switch kicked off meant a 30-minute drive to the data center
- Data recovery bandwidth as fast as a car loaded with tapes could drive
- Didn't update things until something was broke
- Large binders of CDs for every OS and program in the company
- Hotswap was a myth (and no one really used SCSI back then 🤣 )
- Sneakernet

[/r/sysadmin](https://www.reddit.com/r/sysadmin/comments/1f6wvlq/what_was_it_like_to_be_a_sysadmin_in_the_90s_or/) horror stories are fun, if not a bit triggering <br /><br />
[BOFH.](http://www.bofharchive.com/BOFH.html) 'nuf said.

<!--

-->

---
layout: image
image: /img/slides/sneakernet-2x.gif
backgroundSize: contain
---


<!--

-->

---
layout: image
image: /img/slides/cloud-transformation.jpg
backgroundSize: contain
---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


<!--

-->

---


---
layout: end
---
