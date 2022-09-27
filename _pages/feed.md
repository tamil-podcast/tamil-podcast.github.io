---
layout: empty
date: 2015-03-01 00:00:00 +0530
permalink: /feed.xml
---
<?xml version="1.0" encoding="UTF-8"?>
<rss xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:content="http://purl.org/rss/1.0/modules/content/" xmlns:atom="http://www.w3.org/2005/Atom" version="2.0" xmlns:itunes="http://www.itunes.com/dtds/podcast-1.0.dtd" xmlns:anchor="https://anchor.fm/xmlns">
	<channel>
		<title><![CDATA[{{ site.title }}]]></title>
		<description><![CDATA[{{ site.tagline }}]]></description>
        <link>{{ site.url }}</link>
        <image>
            <url>{{ site.podcast-image-url }}</url>
            <title><![CDATA[{{ site.title }}]]></title>
            <link>{{ site.url }}</link>
        </image>
        <generator>Jekyll Liquid Template in Github</generator>
        <pubDate>{{ site.time | date_to_rfc822  }}</pubDate>
        <lastBuildDate>{{ site.time | date_to_rfc822  }}</lastBuildDate>
        <author><![CDATA[{{ site.author }}]]></author>
		<copyright><![CDATA[{{site.copyright}}]]></copyright>
		<category>Blogs</category>
		<language>ta</language>
        <docs>https://cyber.law.harvard.edu/rss/rss.html</docs>
        <managingEditor>{{ site.email }} ({{ site.author }})</managingEditor>
        <webMaster>{{ site.email }} ({{ site.author }})</webMaster>
        <atom:link href="{{ site.url }}/feed.xml" rel="self" type="application/rss+xml" />
        <atom:link rel="hub" href="https://pubsubhubbub.appspot.com/"/>
        <itunes:author><![CDATA[{{ site.author }}]]></itunes:author>
        <itunes:summary><![CDATA[{{ site.tagline }}]]></itunes:summary>
        <itunes:type>episodic</itunes:type>
        <itunes:owner>
            <itunes:name><![CDATA[{{ site.author }}]]></itunes:name>
            <itunes:email><![CDATA[{{ site.email }}]]></itunes:email>
        </itunes:owner>
        <itunes:explicit>No</itunes:explicit>
        <itunes:category text="Society &amp; Culture">
            <itunes:category text="Personal Journals"/>
        </itunes:category>
        <itunes:image href="{{ site.podcast-image-url }}"/>
		{% for post in site.posts limit:10 %}
			<item>
				<title><![CDATA[{{ post.title }}]]></title>
                <description><![CDATA[{{ post.content }}]]></description>
				<link>{{ site.url }}{{ post.url }}</link>
                <guid>{{ site.url }}{{ post.url }}</guid>
                <pubDate>{{ post.date | date_to_rfc822  }}</pubDate>
                <dc:creator><![CDATA[{{ site.author }}]]></dc:creator>
                <enclosure url="{{ post.audio_url }}" length="{{ post.audio_length }}" type="audio/mpeg"/>
                <itunes:summary><![CDATA[{{ post.content }}]]></itunes:summary>
                <itunes:explicit>No</itunes:explicit>
                <itunes:duration>{{ post.audio_duration }}</itunes:duration>
                <itunes:image href="{{ post.image_url }}"/>
                <itunes:season>{{ post.season }}</itunes:season>
                <itunes:episode>{{ post.episode }}</itunes:episode>
                <itunes:episodeType>full</itunes:episodeType>
                <author>{{ site.email }} ({{ site.author }})</author>
				<category>{{ post.category }}</category>
			</item>
		{% endfor %}
	</channel>
</rss>
