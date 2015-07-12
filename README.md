# Wercker build step for hugo themes

This build step for [wercker](http://wercker.com) validates a [hugo](http://gohugo.io) theme.

The script is based on the [hugo build](https://github.com/ArjenSchwarz/wercker-step-hugo-build) step by Arjen Schwarz.

[![wercker status](https://app.wercker.com/status/644025422415f837c19663891770cc29/m "wercker status")](https://app.wercker.com/project/bykey/644025422415f837c19663891770cc29)

## How it works

1. Downloads and installs hugo
1. Creates a new site with a single post
1. The theme is put in the themes folder
1. The `hugo check` command is used to validate the syntax

## Configuration

Every parameter is optional. If you don't provide it, a default value will be used.

* `version` (between quotes): the version of hugo you want to use (default: *the latest version*)
* `name`: the name of your theme (default: *mytheme*)

### Docker stack example

	box: debian
	build:
	  steps:
	    - SamuelDebruyn/hugo-theme-check:
	        version: "0.14"
	        name: redlounge

### Old Wercker stack example

	box: wercker/default
	build:
	  steps:
	    - SamuelDebruyn/hugo-theme-check:
	        version: "0.14"
	        name: redlounge
