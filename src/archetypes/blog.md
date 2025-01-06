+++
title = "{{ replace (slicestr .File.ContentBaseName 11) `-` ` ` | title }}"
slug = "{{ slicestr .File.ContentBaseName 11 }}"
image = "/img/blog/{{ .File.ContentBaseName }}.jpg"
date = '{{ slicestr .File.ContentBaseName 0 10 }}T05:00:00'
publishDate = '{{ slicestr .File.ContentBaseName 0 10 }}T05:00:00'
description = ""
tags = []
+++