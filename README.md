<h1>DNS Tunneling Tracer</h1>

<h2>Introduction</h2>

This project highlights the conceptual mappings of a machine learning model that can be used to track and mitigate DNS tunneling occurances on computer networks. DNS is a prominent protocal established in the 1980s to convert url text strings into IP addresses in order to display and send information. Below I highlight a more comprehensive definition of what DNS tunneling is, its impact on network insecurity, as well as why it should be addressed. As well, I have mapped out the project itself more extensively, breaking down the fields in which features are to be designed around in order to best serve the overall pipeline with high quality and clean information, as well as the algorithmic models we seek to utilize to track and crack these occurances as they occur, as well as source data intended to be utilized in order to solve this problem

As well, this project is to be created without the use of any AI assistance, LLMs or agentic platforms. I am seeking to understand this probelm at its core and how modern day ML algorithmics can be utilized to properly spot abnormalities in DNS traffic. *ALL* reserach and scripting is my own work only.


<h2> DNS Tunneling: In Depth </h2>

in cyber security, DNS tunneling can be described as a method of malicious data extraction in which, once working with a pre-compromised device an attacker can extract information by exploiting the simplicity of DNS protocols. given that DNS is the primary standard for translating human readable URLs into numeric IP addresses, it is highly trusted, and at its core is designed to be as simplistic as possible, as to reduce latency and bottleneck issues when running on older computer networks before the internet took off. As well, having its core origin point of being a small academic computer network back in the 1980s, scaling issues and the very concept that such scale could expose potential informational vulnerabilities was not even under consideration when designing the DNS protocol. For its original purpose, pivoting focus on something workable and low latecy were of sole concern- no different then sending lettermail, so why needlessly convolute the engineering?


Over 40 years later however, the internet (governed by DNS) is now a worldwide phenomenon, and essential for nearly all activities within modern life. despite this explosive scaling, this protocol is still archaic at its core; despite being a essential component for allowing our devices to interact with one another and being used world wide. this leaves lots of room for vulnerability that is easy to exploit, as hidden queires are easy to send through DNS, as modern firewalls do not inspect DNS traffic thouroughly if mcuh at all, usually being more effective when dealing with HTTP/HTTPS. As well, given how prominent DNS traffic is all around, the addition of an encryption layer or other security protocols would only make for a more latent system, thus it is more often than not bypassed by firewalls.


given this, if an attacker is able to place a piece of malware on a host machine and are able to establish a connection on the victims network path, then it can be very easy to read and modify these plain text DNS queries to serve whatever they please. Of course, this means for a method of data extraction that poses difficult to mitigate, going undetected so easily. 

<h2>Importance</h2>

<h1>Project</h1>


<h1>Feature Category Breakdown</h1>


<h2>Query-based Features</h2>
At its core, DNS tunneling as a data extraction method is extremely query heavy: and being query heavy, the very act of encoding data into subdomains is a process that most always leaves a string of bread crumbs in its wake. This could relate to any abnormalities within domains relating to  high entrophy, abnormal character length, or atypical usage patterns within domain names (regular domain names are often short and human readable; the lack of this raises inherent alarm bells all around).


<h4>Potential Features:</h4>
<ul>
<li>subdomain length (tunnelings use of abnormal sized subdomains)</li>
<li>entrophy of subdomain string (embedded data appears randomized)</li>
<li>character distribution (for base64/hex encoding patterns namely)</li>
<li>ratio of numeric/alphabetical characters</li>
<li>presence of abnormal character usage</li>
</ul>

<h2>Domain-based Features</h2>
Next, DNS tunneling being domain top heavy makes this an area critical for further inspection. given that in order to perform such a maneuver, attackers need to register new domain names that are often questionably named (ie: mimicking trusted URLs), this poses yet another node to map out more fully. It is also critical to note along with this that tunnel traffic will often petetrate one sketchy domain in specific with endless and unique subdomains, so this too poses a patterns worth further investigating. On the parallel, legitimate DNS traffic mostly gets channeled to domains that are both aged and well established all around. These two areas are critical to build around to map the domain based area further.

<h4>Potential Features:</h4>
<ul>
<li>domain age/reputation</li>
<li># of unique subdomains queried for an individual domain</li>
<li>depth of subdomain levels (ex: a.b.c.d.roflcopter.com)</li>
</ul>

<h2>Traffic-based Features</h2>
As well, given that we are fundamentally dealing with catching anomalies in network traffic, this raises a checkpoint in which we can investigate to better understand what typical (or atypical) DNS network traffic actually looks like. 

Human beings browse web pages in large bursts over set time intervals, with most traffic following a typical daily trend pattern of some sort. Malware however, saps information in a sturdy and methodical fashion over an automated interval (ie: noteworthy traffic patterns occuring every weekday at 3am would warrant investigation). Ultimately, both traffic and volume in this case are critical pillars (features) that can reveal what patterns in the automation domain look like.

<h4>Potential Features:</h4>
<ul>
<li>query volume per domain (over time)</li>
<li>query frequency + timing patterns</li>
<li>response size (TXT records carrying payloads are much larger)</li>
<li>ratio of query types (ex: heavy TXT/NULL record usage is suspicious)</li>
<li>failed query rates</li>
</ul>

<h2>Behavioural Features</h2>
Beyond splitting hairs over specific patterns that may be exibited by an automated framework to tunnel information over DNS, it is also critical to map out exactly what normal and abnormal traffic actually look like, and differentiate how both humans and machines behave into distinctive categories.

The patterns associated with network traffic patterns themselves matter critically here. If for instance, DNS queries are present that have no associated web activity or originate from an idle workstation at some late night hour, these activities are behaviourlally suspicious and warrant further investigation citing how these operations fundamnetally work.

<h4>Potential Features:</h4>
<ul>
<li>queries occurring at abnormal hours of the day</li>
<li>queries with no corresponding web traffic </li>
<li>single endpoint generating bulk queries to single domain</li>
<li>consistency of query intervals (automated malware vs expected human browsing)</li>
</ul>

<h2>Response Features</h2>
Lastly, at its core DNS tunneling involves the use of DNS responses to send explicit sets of commands. For example, unusual TTLs, larger-than-average TXT files, or response types are often seldomly seem within standard browsing signal trouble. of couse, this is another anomaly that is to be mapped out and addressed.

<h4>Potential Features:</h4>
<ul>
<li>response record types</li>
<li>response payload size</li>
<li>TTL values</li>
</ul>

In essence, these features set out to map out the many areas that make DNS traffic in particular stand out when contrasted against regular traffic patterns that are not of concern. These macro categories ultimately seek to map out the patterns that seed a much larger whole.



