# websh-deno 🦕

A command line [websh](https://github.com/jiro4989/websh) client powered by deno

## Features

- [x] Run commands on the websh environment
- [x] Save execution result images
- [x] Upload local images

## Usage

```
$ websh-deno --help
  Usage:   websh-deno <code:string>
  Version: v0.0.1

  Description:

    A command line websh client powered by Deno

  Options:

    -h, --help     - Show this help.
    -V, --version  - Show the version number for this program.
```

### Run commands

Just specify the command you want to execute in the first argument.

```
$ websh-deno 'uname -a'
Linux e143d8fdbb59 4.15.0-55-generic #60-Ubuntu SMP Tue Jul 2 18:22:20 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
```

### Save execution result images

To save images, output the image files to `/images/` on the websh environment.

```
$ websh-deno 'screenfetch | textimg -o /images/out.png'
Image saved: /tmp/websh-deno_76a6b2f5.png
```

### Upload local images

You can upload and use local images. If you specify the image path in the `-i` / `--images` option and execute it, it will be saved in `0`, `1`, ... files under the `/media/` directory on the websh environment.

```
$ websh-deno --images ~/pic/unko.png --images ~/pic/unkoq.png 'ls -lA /media'
合計 12
-rw-r--r-- 1 root root  828 11月 21 19:21 0
-rw-r--r-- 1 root root 6434 11月 21 19:21 1
```

## Installation

Requires [deno](https://deno.land/deno), testing on `v1.16.1`.

```bash
deno install --allow-net --allow-write --name websh-deno \
    https://raw.githubusercontent.com/sheepla/websh-deno/master/cli.ts
```

... or clone this repository then run below.

```bash
make build && sudo make install
```

## LICENSE

[MIT](./LICENSE)
