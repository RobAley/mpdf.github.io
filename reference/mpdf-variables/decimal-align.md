---
layout: page
title: decimal_align
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/decimal-align.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<h2>Decimal Mark alignment in table columns</h2>
<p>CSS text-align supports decimal mark characters in table cells (TD and TH). HTML attributes "align" and "char" can also be used.</p>
<p>Characters to be used for alignment must be defined in the array <code>$this-&gt;decimal_align</code> in <span class="filename">config.php</span></p>
<p>By default these are : period "."&nbsp; comma&nbsp; ","&nbsp; middot "\B7" and arabic decimal mark "\66B"</p>

{% highlight php %}
<?php

$this->decimal_align = array('DP'=>'.', 'DC'=>',', 'DM'=>"\xc2\xb7", 'DA'=>"\xd9\xab", 'DD'=>'-');
{% endhighlight %}

<p>The default character is a period.</p>
<p>To add additional characters, edit <span class="filename">config.php</span></p>
<ul>
<li>The UTF-8 representation of any non-ASCII characters must be used</li>
<li>Use any unused 2 character code starting with D for the array key</li>
</ul>
</div>
</div>
