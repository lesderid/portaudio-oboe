# PortAudio - portable audio I/O library

PortAudio is a portable audio I/O library designed for cross-platform
support of audio. It uses either a callback mechanism to request audio 
processing, or blocking read/write calls to buffer data between the 
native audio subsystem and the client. Audio can be processed in various 
formats, including 32 bit floating point, and will be converted to the 
native format internally.

## Documentation:

* Documentation is available in "/doc/html/index.html"
* Also see "src/common/portaudio.h" for API spec.
* Also see http://www.portaudio.com/docs/
* And see the "test/" directory for many examples of usage. (we suggest "test/patest_saw.c" for an example)

For information on compiling programs with PortAudio, please see the
tutorial at:

  http://portaudio.com/trac/wiki/TutorialDir/TutorialStart
  
We have an active mailing list for user and developer discussions.
Please feel free to join. See http://www.portaudio.com for details.

## Important Files and Folders:

    include/portaudio.h     = header file for PortAudio API. Specifies API.	
    src/common/             = platform independant code, host independant 
                              code for all implementations.
    src/os                  = os specific (but host api neutral) code
    src/hostapi             = implementations for different host apis


### Host API Implementations:

    src/hostapi/alsa        = Advanced Linux Sound Architecture (ALSA)
    src/hostapi/asihpi      = AudioScience HPI
    src/hostapi/asio        = ASIO for Windows and Macintosh
    src/hostapi/coreaudio   = Macintosh Core Audio for OS X
    src/hostapi/dsound      = Windows Direct Sound
    src/hostapi/jack        = JACK Audio Connection Kit
    src/hostapi/oss         = Unix Open Sound System (OSS)
    src/hostapi/wasapi      = Windows Vista WASAPI
    src/hostapi/wdmks       = Windows WDM Kernel Streaming
    src/hostapi/wmme        = Windows MultiMedia Extensions (MME)


### Test Programs:

    test/pa_fuzz.c         = guitar fuzz box
    test/pa_devs.c         = print a list of available devices
    test/pa_minlat.c       = determine minimum latency for your machine
    test/paqa_devs.c       = self test that opens all devices
    test/paqa_errs.c       = test error detection and reporting
    test/patest_clip.c     = hear a sine wave clipped and unclipped
    test/patest_dither.c   = hear effects of dithering (extremely subtle)
    test/patest_pink.c     = fun with pink noise
    test/patest_record.c   = record and playback some audio
    test/patest_maxsines.c = how many sine waves can we play? Tests Pa_GetCPULoad().
    test/patest_sine.c     = output a sine wave in a simple PA app
    test/patest_sync.c     = test syncronization of audio and video
    test/patest_wire.c     = pass input to output, wire simulator