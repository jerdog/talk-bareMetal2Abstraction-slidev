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
conference: "DevOpsDays Austin 2025"
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
fonts:
  - sans: News Cycle
  - mono: Fira Code
## Current slide
# apply unocss classes to the current slide
class:
  - text-center
  - my-cool-content-on-the-left
layout: image-right
image: /img/slides/legacy-land-default.webp
backgroundSize: contain
layoutClass: openingH2
---

# From Bare Metal to Abstraction
## A There and Back Again Tale to the Heart of Cloud-Native Computing.

<!--
I did entertain the idea of coming out dressed as Gandalf or Bilbo Baggins, but thankfully only for a moment. And don't let my gray beard fool you - this is not going to entirely be a talk about the days of yesteryear. I promise to keep it relevant to today and the future. Plus I only have 20 minutes, so I can't go too far down the rabbit hole. But I do want to take you on a journey through time and space, from the dark ages of IT to the bright future of cloud-native computing. So buckle up, because we're about to embark on an adventure that will make even Bilbo Baggins proud.
-->

---
layout: two-cols
class: text-center
title: "About Me"
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
layout: center
class: text-center
backgroundColor: black
---

A long time ago, in a data center far, far away...{style="color: gold; font-size: 2.5em; line-height: 1.5em;"}


<!--
So, let's start with a little bit of history. A long time ago, in a data center far, far away...
-->

---
layout: image
image: /img/slides/old_stories.jpg
backgroundSize: contain
title: "Old Stories"
---


<!--
So this June marks my 30th year in full-time IT work. Hard to believe, right? I feel  But in all seriousness, how many here are like me and we've spent some time in the industry and have started feeling like the Farmer's Insurance guy, because we know a thing or two because we've see seen a thing or two?
-->

---
layout: image
image: /img/slides/not-the-90s.png
backgroundSize: contain
title: "1990s Data Center Photos"
---


<!--
My first job was literally in a data center in the 90s. I went looking for a picture of a data center in the 90s, because I don't have any photos personally, and I take slight offense at this site and what they classify as "1990s data center photos"... I mean, we did have colour photos back then!
-->

---
title: "Me in the 90s"
layout: center
---

![alt text](/img/slides/me-in-the-90s.jpg){style="resizing: contain; width: 60%; position: relative; margin: auto;"}


<!--
I mean look at me in the 90s! These were my graduation photos from high school in 1995. Not long after these photos were taken, I started working at an Internet Service Provider in Kansas City as Tech Support.
-->

---
title: "Networking Equipment"
layout: center
---

![alt text](/img/slides/networking-equipment.jpg){style="resizing: contain; width: 60%; position: relative; margin: auto;"}

<!--
I eventually moved into the Network Operations Center, and became a SysAdmin and Network Admin and was installing ISDN around KC, using the original IOS (Cisco Internetwork OS) to program Cisco 2500s and 7000s. I even had a Cisco 7000 under my desk and a dedicated T1 - with 1.544 Mbps (megabits per second) transfer rates. Those were the days... Like all of us back then, we were learning on the job! I mean who didn't accidentally mess up internet routes and bring down portions of the internet with routing leaks and route flapping?
-->

---
layout: two-cols-header
class: text-center
layoutClass: gap-8
title: "BGP, the 'Two Napkin Protocol'"
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
In the early 2000s I was at Sprint where I survived 11 years, and ended up being shadow IT for the Network Services department. Who else was "Shadow IT?" Who still is? I started automating and migrating intricate Excel spreadsheets and Access databases to ASP web applications with MySQL and had a whole server farm under my desk. By which I mean 3 Dell OptiPlex desktops fully upgraded running VMWare and VirtualBox.

I couldn't find a good image of what my desk looked like, and only Claude could create one that came close to depicting my cubicle.
-->

---
layout: image
image: /img/slides/dwarves_server_room.jpg
title: "Dwarves Server Room"
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
image: /img/slides/dell-order-screen.png
backgroundSize: contain
title: "Dell Order Screen"
---


<!--
The process to get a server was a long and arduous one. You had to go to Dell's website, customize what you wanted, and then send it over to IT fulfillment, wait for your manager to approve, then wait for the hardware to be ordered, and then shipped - a process that took a few months.
-->

---
layout: image
image: /img/slides/ordering-a-server.jpg
backgroundSize: contain
title: "Ordering a Server"
---

<v-clicks>
  <v-click>&nbsp;</v-click>
  <v-click>&nbsp;</v-click>
</v-clicks>

<!--
Meanwhile you had to submit an IT ticket to let them know a server was being shipped to a specific data center and that you needed space, and then they would eventually assign a rack, [click]and then you would have to submit a different ticket to a different team to schedule a time for you to come into the data center to set it up, and another ticket to get the cabling ran, and another to get an IP address assigned. [click]And if you were lucky, you might get a server within a month or two. But if you were really unlucky, you might have to wait six months or more. And that was before you had to install and configure everything.
-->

---
layout: image
image: /img/slides/no-tech-support.jpg
backgroundSize: contain
title: "No Tech Support"
---


<!--
And that was just building servers in the late 90s and early 2000s. Think about all of the other things we had to do back then. We had to manually configure just about everything, from the network settings to the operating system. And if something went wrong, well, good luck trying to figure out what it was because online docs and support systems weren't available. We didn't have the luxury of cloud providers and their fancy dashboards and APIs. There was no ClickOps. We had to rely on our own wits and a lot of trial and error.
-->

---
title: "The Dark Ages of IT"
layout: center
title: "The Dark Ages of IT"
---

## The Dark Ages of IT

[/r/sysadmin](https://www.reddit.com/r/sysadmin/comments/1f6wvlq/what_was_it_like_to_be_a_sysadmin_in_the_90s_or/) horror stories are fun, if not a bit triggering <br />

[BOFH.](http://www.bofharchive.com/BOFH.html) 'nuf said.

<v-clicks>

- No online documentation
- Power switch kicked off meant a 30-minute drive to the data center
- Data recovery bandwidth as fast as a car loaded with tapes could drive
- Didn't update things until something was broke
- Large binders of CDs for every OS and program in the company
- Hotswap was a myth (and no one really used SCSI back then 🤣 )
- Sneakernet filesharing

</v-clicks>

<!--
Has anyone explored the /r/sysadmin subreddit? It's a treasure trove of horror stories from the dark ages of IT. [click]No documentation. [click]I mean, who doesn't love a good horror story about the time their power switch kicked off and they had to drive 30 minutes to the data center to fix it? [click]Or the time they had to drive to a different state to recover data because the bandwidth was as fast as a car loaded with tapes could drive? [click]We didn't update things until we had to - still don't. [click]And let's not forget about the large binders of CDs for every OS and program in the company. [click]Or the fact that hotswap was a myth, and no one really used SCSI back then. [click]And of course, there was sneakernet.
-->

---
layout: image
image: /img/slides/sneakernet-2x.gif
backgroundSize: contain
title: "Sneakernet"
---


<!--
Who remembers this example of "sneakernet viruses" from Office Space. A masterpiece of cinematoraphy.
-->


---
layout: image
image: /img/slides/cloud-transformation.jpg
backgroundSize: contain
title: "Cloud Transformation"
---


<!--
To say that the landscape of Information Technology infrastructure has profoundly changed over the past three decades would be putting it lightly. What began in the mid-1990s as a tangible world of physical servers requiring manual racking, configuration, and constant hands-on maintenance has evolved into a very
-->

---
layout: image
image: /img/slides/cncf-landscape.png
backgroundSize: contain
title: "CNCF Landscape"
---

<!--
abstracted, automated, service-oriented landscape known as Cloud Native. This evolution represents not merely an incremental improvement but a fundamental shift in how applications are built, deployed, and managed.
-->


---
layout: center
class: text-center
---

> "We are stuck with technology when what we really want is just stuff that works."

 -Douglas Adams

<!--
We started with bare metal servers, and now we have cloud-native computing. But at the end of the day, we just want stuff that works. Thank you Douglas Adams.
-->

---
layout: two-cols
class: text-center
layoutClass: gap-8
title: "Cloud Dashboards"
---

![alt text](/img/slides/gcp-dashboard.webp){style="position: relative; margin: 25% auto;"}

::right::

![alt text](/img/slides/aws-console.png){style="position: relative; margin: 20% auto;"}


<!--
We no longer have to worry about physical servers and data centers. We can spin up new instances in seconds, and we can scale our applications to meet demand without breaking a sweat.
-->

---
layout: image
image: /img/slides/tangled-up-in-wires.webp
backgroundSize: 65%
title: "Tangled Up in Wires"
---


<!--
Well, at least some of us. There's still someone doing that now, but instead of 1 server per app, it's thousands of apps per server. But with this transformation comes a new set of challenges - that are the same as the old challenges in a different way. Security, scalability, cost-management, etc. - they're all still vaild - but the pace of change is much faster than ever before.
-->

---
layout: center
title: "The Journey"
---

## Journey from Bare Metal to Cloud Native

<v-clicks>

- Limitations inherent in managing physical servers
- Adoption of virtualization to improve resource utilization
- Cloud computing brought on-demand compute resources (a virtual Rent-a-Center)
- DevOps movement pushed collaboration and automation, breaking down silos
- Docker & containerization provided a standardized way to package applications
- Orchestration platforms like Kubernetes emerged to manage containers at scale
- ......

</v-clicks>

<!--
This journey from the constraints of bare metal to flexibility of the cloud, where we've abstracted a lot of these things away, all was for a reason, and has had many different stages. [click]It started with the limitations of managing bare metal servers at the scale we had, which led to the [click]rise of virtualization and the ability to run multiple operating systems and applications on a single physical server to improve resource utilization - like blades, VMWare, Virtualbox, etc. [click]This was followed by the option of virtual Rent-a-Center's (aka cloud computing), which allowed us to rent compute resources on demand, rather than having to buy and maintain our own hardware. [click]The rise of DevOps and the cultural shift towards collaboration and automation further accelerated this transformation, breaking down silos between development and operations teams. [click]Docker popularized containerization, so that applications could be further abstracted away in a standardized way, and then we have seen [click]orchestration platforms like Kubernetes emerged to manage these containers at scale. [click]...
-->

---
layout: image
image: /img/slides/cncf-landscape.png
backgroundSize: contain
title: "CNCF Landscape"
---

<!--
These technological and cultural shifts have yielded Cloud Native, characterized by microservices, continuous delivery, automated management, and so much more. We've had to learn new tools, new languages, and new ways of thinking about infrastructure. But core foundational elements are still there and shape our thinking.
-->

---
layout: two-cols-header
layoutClass: gap-8
title: "Core Foundational Elements - Automation"
---

## Core Foundational Elements

### Automation

::left::

<v-click>

### Past

![alt text](/img/slides/disk-installs.jpg){style="width: 70%; position: relative; margin: auto;"}

</v-click>

::right::

<v-click>

### Present

```yml
provider "aws" {
  alias  = "us_east_1"
  region = "us-east-1"
}

module "my_site" {
  source = "git::ssh://git@github.com/......"

  site_domain = "hello.example.com"
}

resource "aws_s3_bucket_object" "my_index" {
  bucket       = "${module.my_site.bucket_name}"
  key          = "index.html"
  content      = "<pre>Hello World!</pre>"
  content_type = "text/html; charset=utf-8"
}

output "bucket_name" {
  description = "S3 bucket name"
  value       = "${module.my_site.bucket_name}"
}
```

</v-click>

<!--
From the early days of manual system administration to today's cloud-native environments, automation has been a driving force. The automation of tasks like deploying new servers or scaling applications helps create faster and more efficient systems. [click]From a sysadmin having to manually install software stacks using stacks of floppy disks.... [click] to the use of Infrastructure as Code (IaC) tools like Terraform, which allow us to define our infrastructure in code and automate the provisioning process based on demand, using tools like Kubernetes to manage containerized applications.
-->

---
layout: two-cols-header
layoutClass: gap-8
title: "Core Foundational Elements - Standardization"
---

## Core Foundational Elements

### Standardization

::left::

<v-click>

### Past

![alt text](/img/slides/diff-ports.jpg){style="width: 60%; position: relative; margin: auto;"}

</v-click>

::right::

<v-click>

### Present

![alt text](/img/slides/REST-API.webp){style="width: 70%; position: relative; margin: auto;"}

</v-click>


<!--
Standardization ensures that different systems and components can work together. Standardized network protocols are what allows all devices to talk to one another. [click]**Past**: Attempting to get different software components or applications to communicate often involved relying on complex, sometimes proprietary, middleware or struggling with disparate protocols, making integration a costly and time-consuming effort. [click]**Present**: Standardized APIs (like REST) and protocols (like HTTP) allow microservices to communicate effectively and easily integrate in a cloud native environment, enabling faster development and deployment of distributed systems.
-->

---
layout: two-cols-header
layoutClass: gap-8
title: "Core Foundational Elements - Scalability"
---

## Core Foundational Elements

### Scalability

::left::

<v-click>

### Past

![alt text](/img/slides/vintage-servers.webp){style="width: 60%; position: relative; margin: auto;"}

</v-click>

::right::

<v-click>

### Present

![alt text](/img/slides/aws-autoscaling.png){style="position: relative; margin: auto;"}

</v-click>


<!--
The ability to increase the capacity of a system to handle greater workloads is crucial. Early systems had limited scaling potential, while cloud native systems are designed for horizontal scalability, and handle sudden spikes in traffic. [click]**Past**: Physical servers having to be provisioned months in advance of expected use. [click]**Present**: Now we have 6 different names to say that a platform has auto-scaling features to automatically adjust resources.
-->

---
layout: two-cols-header
layoutClass: gap-8
title: "Core Foundational Elements - Resilience"
---

## Core Foundational Elements

### Resilience

::left::

<v-click>

### Past

![alt text](/img/slides/veritas.jpg){style="width: 80%; position: relative; margin: auto;"}

</v-click>

::right::

<v-click>

### Present

![alt text](/img/slides/failover-group.png){style="width: 90%; position: relative; margin: auto;"}

</v-click>


<!--
Systems must be able to withstand failures and continue operating. From building redundant systems by hand, to today's cloud platforms with built in fault tolerance. [click]**Past**: Administrators manually configuring back up servers. Who remembers Veritas Backup Exec? [click]**Present**: Cloud environments use clusters of independent instances, data replication and automatic failover in the case of a node outage.
-->

---
layout: two-cols-header
layoutClass: gap-8
title: "Core Foundational Elements - Security"
---

## Core Foundational Elements

### Security

::left::

<v-click>

### Past

![alt text](/img/slides/cisco-pix-515e.jpg){style="position: relative; margin: auto;"}

</v-click>

::right::

<v-click>

### Present

![alt text](/img/slides/devsecops.png)

</v-click>


<!--
Protecting systems and data has always been important, but older security was often an afterthought, while modern cloud systems have security designed in from the start. [click]**Past**: Firewalling off entire networks of computers. [click]**Present**: Zero trust architecture and DevSecOps processes to build security in from the start, not as an afterthought.
-->

---
layout: image
image: /img/slides/gandalf-a-wizard-is-never-late.gif
backgroundSize: 80%
---

<!--
As Gandalf said, We are where we are today because of the journey we've taken, and the lessons we've learned along the way. So for those of you who will be working on the systems of the future, you've arrived at the right time. And I have some thoughts on the challenges we are going to face...
-->

---
title: "Future Challenges"
---

## Future Challenges

<v-clicks>

* Practitioner Experience + AI-Driven Operations
* Expanding Cloud Boundaries
* Sustainability and Efficiency Focus
* Continued Open Ecosystem Growth

</v-clicks>

<!--
[click]**AI-Driven Operations & Developer Experience:** The future involves integrating Artificial Intelligence for more predictive, automated IT operations (AIOps) and adopting platform engineering to manage complexity and provide enhanced self-service capabilities for developers. [click]**Expanding Cloud Boundaries:** Cloud-native principles are extending beyond traditional data centers into edge computing, bringing processing closer to data sources, while technologies like WebAssembly (Wasm) promise lightweight, portable execution for serverless and edge scenarios. [click]**Sustainability and Efficiency Focus:** Optimizing for energy and resource efficiency through GreenOps practices is becoming an increasingly critical consideration within cloud environments. [click]**Continued Open Ecosystem Growth:** Our Open ecosystems are struggling in many cases, and we need to continue to foster open standards and vendor-neutral ecosystems, driving future innovation and ensuring accessibility of cloud-native technologies.
-->

---
layout: center
class: text-center
---

> "I learned to always take on things I’d never done before. <br />Growth and comfort do not coexist."

 -Ginni Rometty, former IBM CEO

<!--
We have to continue to grow and learn, and take on new challenges. We can't get comfortable with the way things are now, because they will change again. And we have to be ready for it.
-->

---
layout: two-cols
layoutClass: gap-8
---


<div style="padding-top:200px; align-items: center; justify-content: center; margin: 0 auto; display: flex;">

  <h2>Thank you!</h2>

</div>

::right::

<div class="text-left" style="padding-left: 75px;">
  <p><img src="/img/bluesky-logo.svg" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px">@jerdog.dev</p>
  <p><img src="/img/linkedin.png" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px">/in/jeremymeiss</p>
  <p><img src="/img/devto.png" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px">@jerdog</p>
  <p><img src="/img/mastodon.png" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px">@jerdog@hachyderm.io</p>
  <p><img src="/img/www.png" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px">jmeiss.me</p>
  <p style="text-decoration: line-through;"><img src="/img/twitter.png" style="vertical-align: middle; display: inline; margin: 5px; max-height:50px; padding-right:10px;">@IAmJerdog</p>
</div>

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
