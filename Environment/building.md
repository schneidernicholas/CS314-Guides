# Building

To build, simply navigate to the root directory of your cloned repo, and run:
```sh
$ ./bin/run.sh
```

## SSH Port Forwarding
If you are not working out of the CS network, you will need to forward ports using SSH so that you can access `black-bottle.cs.colostate.edu` and `faure.cs.colostate.edu`. These machines are behind a network firewall that prevents the outside world from directly connecting, which is why you need to SSH forward ports.

In `~/.ssh/config` add:

```sh
Host cs314
    HostName <CS-Machine>.cs.colostate.edu
    User <EID>
    LocalForward 56247 faure:3306
    LocalForward 31400 black-bottle:31400
    LocalForward 31401 black-bottle:31401
    LocalForward 31402 black-bottle:31402
    LocalForward 31403 black-bottle:31403
    LocalForward 31404 black-bottle:31404
    LocalForward 31405 black-bottle:31405
    LocalForward 31406 black-bottle:31406
    LocalForward 31407 black-bottle:31407
    LocalForward 31408 black-bottle:31408
    LocalForward 31409 black-bottle:31409
    LocalForward 31410 black-bottle:31410
    LocalForward 31411 black-bottle:31411
    LocalForward 31412 black-bottle:31412
    LocalForward 31413 black-bottle:31413
    LocalForward 31414 black-bottle:31414
    LocalForward 31415 black-bottle:31415
    LocalForward 31416 black-bottle:31416
    LocalForward 31417 black-bottle:31417
    LocalForward 31418 black-bottle:31418
    LocalForward 31419 black-bottle:31419
    LocalForward 31420 black-bottle:31420
    LocalForward 31421 black-bottle:31421
    LocalForward 31422 black-bottle:31422
    LocalForward 31423 black-bottle:31423
    LocalForward 31424 black-bottle:31424
    LocalForward 31425 black-bottle:31425
    LocalForward 31426 black-bottle:31426
    LocalForward 31427 black-bottle:31427
    LocalForward 31499 black-bottle:31499
    LocalForward 34200 black-bottle:34200
    LocalForward 34201 black-bottle:34201
    LocalForward 34202 black-bottle:34202
    LocalForward 34203 black-bottle:34203
    LocalForward 34204 black-bottle:34204
    LocalForward 34200 black-bottle:34200
```

**Replace `<CS-Machine>` with a [CS machine](https://www.cs.colostate.edu/machinestats/) and `<EID>` with your EID you SSH into the CS machines with.**

Now, to actively forward those ports, you can run:
```sh
$ ssh cs314
```

You will need to leave this connected/running while developing/building the application. You'll need to reconnect to this each time.
