---
layout: single
title: "Work Smarter Not Harder: Automate Your Photoshop Workflow"
date: 2013-01-04 23:28
author: mrbrant
comments: true
categories: [actions, adobe, adobe bridge, adobe photoshop, automation, Graphic Design, graphic design, photoshop, Photoshop Tutorials]
---
<style type="text/css">
.featured-image {display: none !important;}
</style>

<iframe src="http://player.vimeo.com/video/56801727" width="570" height="320" frameborder="0" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

I have a client with 437 product images on their website, all with rasterized text. What this means is that the text is part of an image rather than HTML text, meaning the search engines cannot read the text. Because of this, their website is not as indexable as it should be by the search engines.

As part of our optimization process, we are optimizing all of their rasterized text into readable text. It is a lot of work, but fortunately parts of it can be automated using Photoshop.

We can use what is called an action in Photoshop to record our workflow (provided all input items will be treated the same way) and then run that action against an input folder and an output folder.

<strong>Within Adobe Photoshop</strong>
<ol>
	<li>Open an example item in Photoshop.</li>
	<li>Navigate to Window &gt; Actions to make sure the actions pane is open</li>
	<li>Within the Actions pane, click the icon for "create new"</li>
	<li>Give the action a name, a set (folder) and click "Record"</li>
	<li>Make the necessary changes to the image - these will be recorded as part of the action</li>
	<li>When you are finished, click the stop icon in the Actions pane</li>
</ol>
<strong>Within Adobe Bridge</strong>
<ol>
	<li>Browse to the input folder of images</li>
	<li>Select all images that the action should be fun on</li>
	<li>Go to Tools &gt; Photoshop &gt; Batch</li>
	<li>Choose the appropriate Set and Action at the top</li>
	<li>Under Destination, choose "Folder" (this is your output folder)</li>
	<li>Browse to the appropriate destination and click "Choose"</li>
	<li>Choose the file naming convention for the output file - if you want it to remain the same then choose "Document Name" + "extension".</li>
	<li>Do not check any of the checkboxes</li>
	<li>Choose "Ok" in the top right corner to run the action</li>
</ol>
If everything goes well and there are no errors, check your output folder once the action completes.
