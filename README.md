# bar3x

`bar3x` is an easy to use and powerful status bar for your Linux desktop written in Golang.
Linux status bars typically choose between highly customizable text and richt graphics. `bar3x` takes a slightly different approach by providing a simple markup language for its configuration that allows for :

- Easy addition of new built-in modules
- Rich external command modules
- Customizable graphics

## Installing

_todo: releases_

### Dependencies

- [libcairo](https://www.cairographics.org/) : should already installed as it is used by GTK, otherwise:
  - Debian/Ubuntu: `apt install libcairo2`
  - Fedora: `yum install cairo`
  - Arch: `pacman -S cairo`

## Configuration

`bar3x` comes with a default configuration, and can be customized using `bar3x -config config.yaml` to change part or all of these parameters. Here is an example config :

```yaml

// colors configuration
bg_color:            "#17191e" // bar background
text_color:          "#d4e5f7" // general text
accent_color:        "#1ebce8" // icons and UI elements such as bars
neutral_color:       "#37393e" // background elements such as module separators and background graphs
neutral_light_color: "#90949d" // used for less important text such as units

// modules can be placed on the left, center and right of the bar
bar_left: |
  <ModuleRow>
    <Music />
    <Volume />
  </ModuleRow>

bar_center: |
  <ModuleRow>
    <Date />
  </ModuleRow>

bar_right: |
  <ModuleRow>
    <Interface Iface="enp3s0" />
    <CPU />
    <RAM />
    <DiskUsage />
  </ModuleRow>
```