# Jackett Search Cli
A cli tool to search torrents made with the [jackett](https://github.com/Jackett/Jackett) api

# Installation

- Install the dependencies (jq, fzf, jackett)
- Add some indexers to jackett
- Copy your api key
- Download the script
 
  ```shell
  wget https://raw.githubusercontent.com/rodrigo-sys/jsc/main/jcs
  ```
- Open it
- Change 'YOUR_API_KEY_HERE' string, in the second line for you jackett api key
- Put the script in somewhere in your path 
   
# Usage 
```shell
jsc <search_term>
```
if you want to filter by tracker:

```shell
jsc -t <tracker> -s <search_term>
```

# Examples

```shell
jsc -t rarbg -s 'palm springs'
```

(you need to use quotes if the search have spaces)

```shell
jsc palm springs
```

(you dont need quotes when not uses flags)

# Tips
This program just output the magnet link of the selected result.

But if you want...

- Stream 
  * With [webtorrent](https://github.com/webtorrent/webtorrent-clii)
 
  ```shell
  jsc palm springs | xargs -r webtorrent --mpv
  ```
  
  * With [mpv-webtorrent-hook](https://github.com/mrxdst/webtorrent-mpv-hook)
  
  ```shell
    jsc queen gambit | xargs -r mpv
  ```
 
- Download 
 
  ```shell
  jsc palm springs | xargs -r xdg-open 
 
  ```
  
  or
 
  ```shell
  jsc palm springs | xargs -r <torrent_client>
 
  ```
  
Make functions to make easy:
 
```shell
netflix(){
  jsc "$@" | xargs -r webtorrent --mpv
}
```
```shell
piratebay(){
  jsc "$@" | xargs -r xdg-open 
}
```

# Dependencies
- jq
- fzf
- jackett

# Demo

(click the image)

[![jsc demo](https://img.youtube.com/vi/YpXuCSzH4A0/maxresdefault.jpg)](https://www.youtube.com/embed/YpXuCSzH4A0)

# TODO
- [ ] Improve readme
- [ ] Make the demo a gif 
- [ ] Share in social media 
- [ ] Maybe add stream and open flag

G
