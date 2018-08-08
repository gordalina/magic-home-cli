# Magic Home

## Install

```bash
npm install -g @gordalina/magic-home-cli
# or
yarn add global @gordalina/magic-home-cli
```

## Scan

To find lights use the `scan` command, it accepts an optional `--timeout`
argument (in milliseconds) as well as a `--json` for JSON formatted output.

```bash
$ magic-home scan [--json] [--timeout 500]
Found light at '192.168.1.42' with model 'AK001-ZJ200' and id='721134581243'
```

# Interact

You can turn on/off the light as well as set colors and patterns.

```bash
# Turn on
$ magic-home 192.168.1.42 on

# Turn off
$ magic-home 192.168.1.42 on

# Query state
$ magic-home 192.168.1.42 state
{
  "on": true,
  "mode": "color",
  "speed": 50,
  "color": {
    "red": 255,
    "green": 0,
    "blue": 207
  },
  "warm_white_percent": 0
}

# Set a color
$ magic-home 192.168.1.42 color 255 0 207

# Set a color with 50% brightness
$ magic-home 192.168.1.42 color 255 0 207 50

# Set a pattern
$ magic-home 192.168.1.42 pattern blue_stobe_flash 75

# List patterns
$ magic-home patterns [--json]
seven_color_cross_fade
red_gradual_change
green_gradual_change
blue_gradual_change
yellow_gradual_change
cyan_gradual_change
purple_gradual_change
white_gradual_change
red_green_cross_fade
red_blue_cross_fade
green_blue_cross_fade
seven_color_strobe_flash
red_strobe_flash
green_strobe_flash
blue_stobe_flash
yellow_strobe_flash
cyan_strobe_flash
purple_strobe_flash
white_strobe_flash
seven_color_jumping
```
