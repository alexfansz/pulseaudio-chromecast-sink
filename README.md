PulseAudio sink for Chromecast
==============================

Application for creating virtual audio sinks in PulseAudio that send all
audio to Google Chromecast Audio.

Application is in development stage. There is still some work to be done before
it will be usable by end users. The biggest issue right now is that, Chromecast
receiver app is not published yet. If you want to use this application right
now, you have register it in Google Cast SDK Developer Console and host code
on your own.

If you want to help in development, look for TODOs in code. There is also a lot
of refactoring work needed.

Build
-----

This program requires following libraries to be installed in your
system: Asio (standalone), libavahi-client, libpulse, protobuf-lite, spdlog,
OpenSSL, WebSocket++, nlohmann/json, gflags.

The build process also requires `protoc` protobuf compiler to be installed.

    $ git clone https://github.com/p2004a/pulseaudio-chromecast-sink
    # cd pulseaudio-chromecast-sink
    $ mkdir build
    $ cd build
    $ cmake .. -DCMAKE_BUILD_TYPE=Release
    $ make -j

Development
-----------

### Code style

The code style is defined in [.clang-format](./.clang-format) file. All code
should be formatted using clang-format with that style file.

To format all code in this repository you can run provided script:

    $ ./format-all.sh

To make sure that you never commit incorrectly formatted code you can set up
simple [pre-commit hook](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
script from this repository:

    $ ln -s ../../pre-commit.py .git/hooks/pre-commit

The script requires python >= 3.4 installed in your system.

License
-------

For licensing information see file [COPYING.txt](COPYING.txt).
