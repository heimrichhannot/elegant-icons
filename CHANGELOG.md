# Changelog
All notable changes to this project will be documented in this file.

## [1.3.5] - 2017-12-18

### Fixed
- dropped obsolete font files `elegant-icons`
- restored misspelled css classes and scss, less variables

## [1.3.4] - 2017-12-18

### Fixed
- restored @ei-var-circle-slelected at variables.less

## [1.3.3] - 2017-12-18

### Fixed
- spelling mistakes in less

## [1.3.2] - 2017-12-05

### Fixed
- less variables for updated elegant icons font (see 1.2.0)

## [1.3.1] - 2017-12-04

### Fixed
- Updated elegant icons generated css classes `ei-*`

## [1.3.0] - 2017-11-30

### Changed
- Contao 4 version of 1.2.0 tag, changed sass font path to `/assets/elegant-icons/fonts`
- for contao 3 support, use 1.2.x versions, this is locked to contao/core

## [1.2.0] - 2017-11-30

### Changed
- Updated local fonts, to fit fonts from `CDN` (also added woff2 file)
- Sass now loads fonts from local location instead of `CDN`
- locked 1.2 version to contao 3.x as components are installed to `assets/components` (contao 4 to `assets`, new version 1.3) and font-path must fit 
