# ZModem integration for iTerm 2

Transfer files using Z-Model from within iTerm2 to any remote machine
with `lrzsz` installed.

## Installation
Installing from [Homebrew][homebrew] tap [laggardkernel/tap][laggardkernel/tap]
is recommended. It solves the dependency (`lrzsz`) automatically.

```shell
brew install laggardkernel/tap/iterm2-zmodem
```

Then, follow the output from the above command to do the post-setup.

## Troubleshooting
- Sending a directory may fail: this is a known issue
- If you are using tmux or some other terminal multiplexer (ie: `screen`),
  try using the `-e` option to `sz` and/or `rz` on your server to
  force escaping of more characters during transmission.
- This tool may also fail if you are using `expect` or `rlogin` as
  it expects a mostly-clean 8-bit connection between the two parties.

## Origin

The talk made by [mmastrac][mmastrac] about "a free Taiwan and a free Tibet"
in the [luxihk/iterm2-zmodem][luxihk/iterm2-zmodem] repo irritates many people,
after they made the decision to bombard the users by printing the content to
the STDOUT whenever `sz` or `rz` is typed.

[homebrew]: https://brew.sh/
[laggardkernel/tap]: https://github.com/laggardkernel/homebrew-tap
[mmastrac]: https://github.com/mmastrac
[luxihk/iterm2-zmodem]: https://github.com/luxihk/iterm2-zmodem
