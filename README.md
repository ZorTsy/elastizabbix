# elastizabbix
Down and dirty elastic / elasticsearch monitoring plugin for zabbix

> Forked from: https://github.com/mkhpalm/elastizabbix

## Features:

- Stats cache to avoid saturating nodes with monitoring requests
- Node and index low-level (auto) discovery
- JSON-like dot notation item syntax for easy customization
- Can monitor anything elastic exposes in the stats API

## Requirements

 - Python 2/3 on an elastic node with zabbix agent installed
	 - or you can install on your Zabbix server and set up the remote URL to be monitored

## Installation

This only needs to be setup on one of the elasticsearch nodes or on the Zabbix server

#### Zabbix Agent

- Copy elastizabbix to agent scripts folder
- Copy elastizabbix.conf to conf.d or add UserParameter to your agent config
- Restart the Zabbix Agent

#### Zabbix Frontend

- Import the XML template (tested on Zabbix 3.0)
- Add node to the newly imported template
- Change the node macro `{$ES.CLUSTER.URL}` to your cluster address `http://localhost:9200`

## The MIT License (MIT)

Copyright (c) 2015 Mike Palmer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
