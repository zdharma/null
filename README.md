# null
An empty repository to aid zplugin's hooks-hacks.

# Example uses:

1. When what's needed is an `atclone''` hook to e.g. install a software (plus `atpull''` hook to update it):

```zsh
zplugin ice as"program" pick"$ZPFX/sdkman/bin/sdk" id-as'sdkman' run-atpull \
  atclone"wget https://get.sdkman.io -O scr.sh; SDKMAN_DIR=$ZPFX/sdkman bash scr.sh" \
  atpull"SDKMAN_DIR=$ZPFX/sdkman sdk selfupdate" \
  atinit"SDKMAN_DIR=$ZPFX/sdkman source $ZPFX/sdkman/bin/sdkman-init.sh"
zplugin light zdharma/null
```
