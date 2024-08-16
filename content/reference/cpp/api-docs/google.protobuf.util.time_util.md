+++
title = "time_util.h"
toc_hide = "true"
linkTitle = "C++"
description = "This section contains reference documentation for working with protocol buffer classes in C++."
type = "docs"
+++

<p><code>#include &lt;google/protobuf/util/time_util.h&gt;<br>namespace <a href="#google.protobuf.util">google::protobuf::util</a></code></p><p>Defines utilities for the Timestamp and Duration well known types. </p><table width="100%"><tr><th colspan="2"><h3 style="margin-top: 4px">Classes in this file</h3></th></tr><tr><td><div><code><a href="#TimeUtil">TimeUtil</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Utility functions for Timestamp and Duration. </div></td></tr></table><h2 id="TimeUtil">class TimeUtil</h2><p><code>#include &lt;<a href="#">google/protobuf/util/time_util.h</a>&gt;<br>namespace <a href="#google.protobuf.util">google::protobuf::util</a></code></p><p>Utility functions for Timestamp and Duration. </p><table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>const int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.kTimestampMinSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>kTimestampMinSeconds</b> = = -62135596800LL</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">The min/max Timestamp/Duration values we support.  <a href="#TimeUtil.kTimestampMinSeconds.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>const int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.kTimestampMaxSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>kTimestampMaxSeconds</b> = = 253402300799LL</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">For "9999-12-31T23:59:59.999999999Z". </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>const int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.kDurationMinSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>kDurationMinSeconds</b> = = -315576000000LL</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>const int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.kDurationMaxSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>kDurationMaxSeconds</b> = = 315576000000LL</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static std::string</code></td><td style="border-left-width: 0px"id="TimeUtil.ToString"><div style="padding-left: 16px; text-indent: -16px"><code><b>ToString</b>(const Timestamp &amp; timestamp)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Converts Timestamp to/from RFC 3339 date string format.  <a href="#TimeUtil.ToString.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static bool</code></td><td style="border-left-width: 0px"id="TimeUtil.FromString"><div style="padding-left: 16px; text-indent: -16px"><code><b>FromString</b>(const std::string &amp; value, Timestamp * timestamp)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static std::string</code></td><td style="border-left-width: 0px"id="TimeUtil.ToString"><div style="padding-left: 16px; text-indent: -16px"><code><b>ToString</b>(const Duration &amp; duration)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Converts Duration to/from string format.  <a href="#TimeUtil.ToString.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static bool</code></td><td style="border-left-width: 0px"id="TimeUtil.FromString"><div style="padding-left: 16px; text-indent: -16px"><code><b>FromString</b>(const std::string &amp; value, Duration * timestamp)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.GetCurrentTime"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetCurrentTime</b>()</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Gets the current UTC time. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.GetEpoch"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetEpoch</b>()</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Returns the Time representing "1970-01-01 00:00:00". </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.NanosecondsToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>NanosecondsToDuration</b>(int64_t nanos)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Converts between Duration and integer types.  <a href="#TimeUtil.NanosecondsToDuration.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.MicrosecondsToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>MicrosecondsToDuration</b>(int64_t micros)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.MillisecondsToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>MillisecondsToDuration</b>(int64_t millis)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.SecondsToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>SecondsToDuration</b>(int64_t seconds)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.MinutesToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>MinutesToDuration</b>(int64_t minutes)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.HoursToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>HoursToDuration</b>(int64_t hours)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToNanoseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToNanoseconds</b>(const Duration &amp; duration)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Result will be truncated towards zero.  <a href="#TimeUtil.DurationToNanoseconds.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToMicroseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToMicroseconds</b>(const Duration &amp; duration)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToMilliseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToMilliseconds</b>(const Duration &amp; duration)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToSeconds</b>(const Duration &amp; duration)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToMinutes"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToMinutes</b>(const Duration &amp; duration)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToHours"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToHours</b>(const Duration &amp; duration)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.NanosecondsToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>NanosecondsToTimestamp</b>(int64_t nanos)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Creates Timestamp from integer types.  <a href="#TimeUtil.NanosecondsToTimestamp.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.MicrosecondsToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>MicrosecondsToTimestamp</b>(int64_t micros)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.MillisecondsToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>MillisecondsToTimestamp</b>(int64_t millis)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.SecondsToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>SecondsToTimestamp</b>(int64_t seconds)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToNanoseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToNanoseconds</b>(const Timestamp &amp; timestamp)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Result will be truncated down to the nearest integer value.  <a href="#TimeUtil.TimestampToNanoseconds.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToMicroseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToMicroseconds</b>(const Timestamp &amp; timestamp)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToMilliseconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToMilliseconds</b>(const Timestamp &amp; timestamp)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static int64_t</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToSeconds"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToSeconds</b>(const Timestamp &amp; timestamp)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.TimeTToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimeTToTimestamp</b>(time_t value)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Conversion to/from other time/date types.  <a href="#TimeUtil.TimeTToTimestamp.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static time_t</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToTimeT"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToTimeT</b>(const Timestamp &amp; value)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Timestamp</code></td><td style="border-left-width: 0px"id="TimeUtil.TimevalToTimestamp"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimevalToTimestamp</b>(const timeval &amp; value)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Conversion to/from timeval. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static timeval</code></td><td style="border-left-width: 0px"id="TimeUtil.TimestampToTimeval"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimestampToTimeval</b>(const Timestamp &amp; value)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static Duration</code></td><td style="border-left-width: 0px"id="TimeUtil.TimevalToDuration"><div style="padding-left: 16px; text-indent: -16px"><code><b>TimevalToDuration</b>(const timeval &amp; value)</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static timeval</code></td><td style="border-left-width: 0px"id="TimeUtil.DurationToTimeval"><div style="padding-left: 16px; text-indent: -16px"><code><b>DurationToTimeval</b>(const Duration &amp; value)</code></div></td></tr></table> <hr><h3 id="TimeUtil.kTimestampMinSeconds.details"><code>const int64_t TimeUtil::kTimestampMinSeconds = = -62135596800LL</code></h3><div style="margin-left: 16px"><p>The min/max Timestamp/Duration values we support. </p><p>For "0001-01-01T00:00:00Z". </p>
</div> <hr><h3 id="TimeUtil.ToString.details"><code>static std::string TimeUtil::ToString(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const Timestamp &amp; timestamp)</code></h3><div style="margin-left: 16px"><p>Converts Timestamp to/from RFC 3339 date string format. </p><p>Generated output will always be Z-normalized and uses 3, 6 or 9 fractional digits as required to represent the exact time. When parsing, any fractional digits (or none) and any offset are accepted as long as they fit into nano-seconds precision. Note that Timestamp can only represent time from 0001-01-01T00:00:00Z to 9999-12-31T23:59:59.999999999Z. Converting a Timestamp outside of this range is undefined behavior. See <a href='https://www.ietf.org/rfc/rfc3339.txt'>https://www.ietf.org/rfc/rfc3339.txt</a>.</p>

<p>Example of generated format: </p>

<pre>"1972-01-01T10:00:20.021Z"</pre>

<p>Example of accepted format: </p>

<pre>"1972-01-01T10:00:20.021-05:00"</pre>
</div> <hr><h3 id="TimeUtil.ToString.details"><code>static std::string TimeUtil::ToString(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const Duration &amp; duration)</code></h3><div style="margin-left: 16px"><p>Converts Duration to/from string format. </p><p>The string format will contains 3, 6, or 9 fractional digits depending on the precision required to represent the exact Duration value. For example: </p>
<pre>"1s", "1.010s", "1.000000100s", "-3.100s"</pre>

<p> The range that can be represented by Duration is from -315,576,000,000 to +315,576,000,000 inclusive (in seconds). </p>
</div> <hr><h3 id="TimeUtil.NanosecondsToDuration.details"><code>static Duration TimeUtil::NanosecondsToDuration(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;int64_t nanos)</code></h3><div style="margin-left: 16px"><p>Converts between Duration and integer types. </p><p>The behavior is undefined if the input value is not in the valid range of Duration. </p>
</div> <hr><h3 id="TimeUtil.DurationToNanoseconds.details"><code>static int64_t TimeUtil::DurationToNanoseconds(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const Duration &amp; duration)</code></h3><div style="margin-left: 16px"><p>Result will be truncated towards zero. </p><p>For example, "-1.5s" will be truncated to "-1s", and "1.5s" to "1s" when converting to seconds. It's undefined behavior if the input duration is not valid or the result exceeds the range of int64. A duration is not valid if it's not in the valid range of Duration, or have an invalid nanos value (i.e., larger than 999999999, less than -999999999, or have a different sign from the seconds part). </p>
</div> <hr><h3 id="TimeUtil.NanosecondsToTimestamp.details"><code>static Timestamp TimeUtil::NanosecondsToTimestamp(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;int64_t nanos)</code></h3><div style="margin-left: 16px"><p>Creates Timestamp from integer types. </p><p>The integer value indicates the time elapsed from Epoch time. The behavior is undefined if the input value is not in the valid range of Timestamp. </p>
</div> <hr><h3 id="TimeUtil.TimestampToNanoseconds.details"><code>static int64_t TimeUtil::TimestampToNanoseconds(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const Timestamp &amp; timestamp)</code></h3><div style="margin-left: 16px"><p>Result will be truncated down to the nearest integer value. </p><p>For example, with "1969-12-31T23:59:59.9Z", TimestampToMilliseconds() returns -100 and TimestampToSeconds() returns -1. It's undefined behavior if the input Timestamp is not valid (i.e., its seconds part or nanos part does not fall in the valid range) or the return value doesn't fit into int64. </p>
</div> <hr><h3 id="TimeUtil.TimeTToTimestamp.details"><code>static Timestamp TimeUtil::TimeTToTimestamp(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;time_t value)</code></h3><div style="margin-left: 16px"><p>Conversion to/from other time/date types. </p><p>Note that these types may have a different precision and time range from Timestamp/Duration. When converting to a lower precision type, the value will be truncated to the nearest value that can be represented. If the value is out of the range of the result type, the return value is undefined.</p>

<p>Conversion to/from time_t </p>

</div>