# freedv-integrations Changelog

## v2.4.1 October 2026

1. Bugfixes:
    * FreeDV Reporter: fix possible crash when repeatedly connecting and disconnecting. (freedv-backend PR #44)
    * FreeDV Reporter: give up on setting up the secure connection after 10 seconds, so exiting no longer waits up to 60 seconds on a stalled server. (freedv-backend PR #63)
    * FreeDV Reporter: fix memory leaks when a connection closes before it finishes connecting, or while tasks are still queued. (freedv-backend PR #75)
    * FreeDV Reporter: refuse a secure connection if TLS 1.2 or certificate hostname checking can't be enforced. (freedv-backend PR #78)
    * Fix buffer overruns when one RADE receive call decodes several frames and when resampling audio by large ratios. (freedv-backend PR #78)
    * Fix the audio pipeline rebuilding its resampler when the sample rate is unchanged but not when it changes, and freeing the kept resampler twice. (freedv-backend PR #78)
    * Fix network and threading code continuing after a failed socket or semaphore setup, and semaphore waits ending early on a signal. (freedv-backend PR #78)
    * Fix conversion of 16-bit audio to floating point going slightly past full scale. (freedv-backend PR #60)
2. Build system:
    * Fix build errors with GCC 16 and with OpenSSL 4 deprecations. (freedv-backend PR #41, #73)
    * Download RNNoise from its new location. (freedv-backend PR #76)
3. Other:
    * Audio pipeline performance improvements, including RNNoise picking the fastest code for the CPU at runtime on Arm. (freedv-backend PR #40, #42, #43, #45, #46, #47, #52, #53, #61, #64, #65)
    * Log from the audio threads without blocking them. (freedv-backend PR #60)

## v2.4.0 August 2026

1. Bugfixes:
    * Revert r8brain audio sampler for further audio quality improvement. (PR #3)
    * Flex: Update audio limiting logic and restrict to only microphone audio. (PR #10)
    * Fix memory leaks in integrations. (PR #4)
    * Integrate improvements to EOO/callsign reporting. (PR #4, #5)
    * Flex: Enable SNR meter even if reporting is disabled. (PR #6)
    * Flex: Only go into TX if the client with the FDV slice is transmitting. (PR #12)
2. Feature enhancements:
    * Enable UDP broadcast of received callsigns if FreeDV Reporter is enabled. (PR #1, #8)
    * Flex: allow some command line arguments to be passed via the environment. (PR #5)
    * Connect to FreeDV Reporter using TLS. (PR #11)
3. Build system:
    * Require C++20 to build integrations. (PR #14)

## Earlier than v2.4.0

See [freedv-gui release notes](https://github.com/drowe67/freedv-gui/blob/master/USER_MANUAL.md#release-notes).
