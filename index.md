---
layout: lesson
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
venue: Online
address: 
country: "UK"
language: "English"
latlng: 
humandate: 10:00-16:00 GMT, 8 - 9 December 2020
humantime: 10:00-16:00 GMT
startdate: 2020-12-08
enddate: 2020-12-09
instructor: ["Andy Turner", "Jeremy Cohen"]
helper: []
email: ["support@archer2.ac.uk"]
collaborative_notes: https://pad.archer2.ac.uk/p/2020-12-08-Containers-Online
---
<h2>Description</h2>

This course aims to introduce the use of containers with the goal of using them to effect reproducible computational environments. Such environments are useful for ensuring reproducible research outputs and for simplifying the setup of complex software dependencies across different systems. The course will mostly be based around the use of Docker containers but the material will be of use for whatever container technology you plan to, or end up, using. We will also briefly introduce the Singularity container environment which is compatible with Docker and designed for use on multi-user systems (such as HPC resources). On completion of this course attendees should:

  - Understand what containers are and what they are used for
  - Understand how to manage and create Docker containers
  - Appreciate decisions that need to be made around containerising research workflows
  - Understand the differences between Docker and Singularity containers and why Singularity is more suitable for multi-user systems (e.g. HPC)
  - Understand how to manage and create Singularity containers
  - Appreciate how containers can be used to enable and improve reproducibility in research

<h2 id="general">General Information</h2>

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  This course will be taught online via Blackboard Collaborate. All attendees will
  be sent the joining link prior to the event.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by the <a href="https://www.archer2.ac.uk/training/code-of-conduct/">ARCHER2 Training Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
</p>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you please get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

> ## Prerequisites
>
> - You should have basic familiarity with using a command shell, and the lesson text will at times request that you "open a shell window", with an assumption that you know what this means.
>   - Under Linux or macOS it is assumed that you will access a `bash` shell (usually the default), using your Terminal application.
>   - Under Windows, Powershell and Git Bash should allow you to use the Unix instructions.
> - As an item of setup, it is assumed that you have a directory named `container-playground` that you are able to `cd` to using your command shell, *and* are also able to find using your computer's graphical file browser (e.g., Finder on macOS or Windows Explorer). A simple way to achieve this is to create your `container-playground` directory within your computer's `Desktop` folder. (See the [Software Carpentry Shell lesson](https://swcarpentry.github.io/shell-novice/) for more details.)
> - The lessons will sometimes request that you use a text editor to create or edit files in particular directories. It is assumed that you either have an editor that you know how to use that runs within the working directory of your shell window (e.g. `nano`), or that if you use a graphical editor, that you can use it to read and write files into the working directory of your shell.
{: .prereq}

<h2 id="setup">Getting Started</h2>

<p>To get started, follow the directions on the <a href="setup.html">Setup</a> page to ensure you have installed the Docker software, have registered for a Dockerhub account, have an SSH client available and have registered a user account on ARCHER2 (the HPC
facility we will be using for the Singularity part of the course).</p>

<hr/>


{% include links.md %}

{% comment %}

TODO: systematically check for Windows-isms

<!--  LocalWords:  prereq links.md endcomment
 -->
{% endcomment %}
