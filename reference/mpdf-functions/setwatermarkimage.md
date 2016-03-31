---
layout: page
title: SetWatermarkImage()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/setwatermarkimage.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p>(mPDF &gt;= 2.2)</p>
<p>SetWatermarkImage – Set an image to use as a Watermark</p>
<h2>Description</h2>

<div class="alert alert-info" role="alert">void <b>SetWatermarkImage</b> ( string <span class="parameter">$src</span> [, float <span class="parameter">$alpha</span> [, mixed <span class="parameter">$size</span> [, mixed <span class="parameter">$position</span> ]]])</div>
<p>Set an image to use as a Watermark. The watermark is a semi-transparent background printed on each page, used for text such as "DRAFT" or a background image. The watermark will be added to each page when the Footer is printed if the variable <a href="{{ "/reference/mpdf-variables/showwatermarktext.html" | prepend: site.baseurl }}">showWatermarkImage</a> is set to 1 or <span class="smallblock">TRUE</span>.&nbsp;</p>
<h2>Parameters</h2>
<p class="manual_param_dt"><span class="parameter">src</span></p>
<p class="manual_param_dd">This parameter specifies the image file to use for the watermark. This can be a full URI or use a relative path<span class="smallblock">

</span></p>
<p class="manual_param_dt"><span class="parameter">alpha</span></p>
<p class="manual_param_dd">This parameter defines the transparency value (alpha) to use for the watermark. The Value should be between 0 and 1.

<span class="smallblock">DEFAULT</span>: 0.2</p>
<p class="manual_param_dt"><span class="parameter">size</span></p>
<p class="manual_param_dd">This parameter takes either a pre-defined string, an integer, or an array of width and height. Defines the size of the watermark.</p>
<p class="manual_param_dd"><b>Values</b>

D: default i.e. original size of image - may depend on <a href="{{ "/reference/mpdf-variables/img-dpi.html" | prepend: site.baseurl }}">img_dpi</a>

P: Resize to fit the full page size, keeping aspect ratio

F: Resize to fit the print-area (frame) respecting current page margins, keeping aspect ratio

<span class="smallblock">INT</span>: Resize to full page size minus a margin set by this integer in millimeters, keeping aspect ratio

array(<span class="parameter">$width</span>, <span class="parameter">$height</span>): Specify a size; units in millimeters

<span class="smallblock">DEFAULT</span>: "D"</p>
<p class="manual_param_dt"><span class="parameter">position</span></p>
<p class="manual_param_dd">This parameter takes either a pre-defined string or an array of <span class="parameter">x</span> and <span class="parameter">y</span>. Defines the position of the watermark on the page.</p>
<p class="manual_param_dd"><b>Values</b>

P: Centred on the whole page area

F: Centred on the page print-area (frame) respecting page margins

array(<span class="parameter">$x</span>, <span class="parameter">$y</span>): Specify a position; units in millimeters

<span class="smallblock">DEFAULT</span>: "P"</p>
<h2>Changelog</h2>
<table class="bpmTopic"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.2</td>
<td>The function was added.</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF();

$mpdf->SetWatermarkImage('../images/background.jpg');

$mpdf->showWatermarkImage = true;

$mpdf->WriteHTML('<p>Hallo World</p>');

?>
{% endhighlight %}

{% highlight php %}
Example #2 - Using a Watermark as a Header

{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF('','A4','','',20,20,50,10);

// Setting transparency to 1, and exact positioning, you can use a Watermark Image as a 'Header'

// Note that the page top-margin is set to accomodate the image

$mpdf->SetWatermarkImage('http://www.yourdomain.com/images/logo.jpg', 1, '', array(160,10));

$mpdf->showWatermarkImage = true;

$mpdf->WriteHTML('<p>Hallo World</p>');

?>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/setwatermarktext.html" | prepend: site.baseurl }}">SetWatermarkText()</a> - Set the text to use as a Watermark</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/setwatermarktext.html" | prepend: site.baseurl }}"></a></li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/watermarkimagealpha.html" | prepend: site.baseurl }}">watermarkImageAlpha</a> - Specifies the transparency (alpha value) for the watermark image</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/watermarktextalpha.html" | prepend: site.baseurl }}">watermarkTextAlpha</a> - Specifies the transparency (alpha value) for the watermark text</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/showwatermarktext.html" | prepend: site.baseurl }}">showWatermarkText</a> - Specifies whether or not to show/print the watermark text

</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/showwatermarktext.html" | prepend: site.baseurl }}">showWatermarkImage</a> - Specifies whether or not to show/print the watermark image</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/watermark-font.html" | prepend: site.baseurl }}">watermark_font</a> - Specifies the font to use for Watermark text</li>
</ul>
</div>
</div>
