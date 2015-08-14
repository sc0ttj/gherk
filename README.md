# gherk
[![Release Version](https://img.shields.io/badge/version-0.1.1-blue.svg)](https://github.com/bakerface/gherk)
[![NPM Version](https://badge.fury.io/js/gherk.svg)](http://badge.fury.io/js/gherk)
[![Build Status](https://travis-ci.org/bakerface/gherk.svg?branch=master)](https://travis-ci.org/bakerface/gherk)
[![Code Climate](https://codeclimate.com/github/bakerface/gherk/badges/gpa.svg)](https://codeclimate.com/github/bakerface/gherk)
[![Test Coverage](https://codeclimate.com/github/bakerface/gherk/badges/coverage.svg)](https://codeclimate.com/github/bakerface/gherk/coverage)
[![GitHub issues](https://img.shields.io/github/issues/bakerface/gherk.svg)](https://github.com/bakerface/gherk/issues)
[![dependencies](https://david-dm.org/bakerface/gherk.svg)](https://david-dm.org/bakerface/gherk)
[![devDependencies](https://david-dm.org/bakerface/gherk/dev-status.svg)](https://david-dm.org/bakerface/gherk#info=devDependencies)
[![Downloads](http://img.shields.io/npm/dm/gherk.svg)](https://www.npmjs.com/package/gherk)

```
# drink.feature

Feature: Can drink beer when thirsty
  As a drinker
  I want to take beer off the wall
  In order to satisfy my thirst

  Scenario: Can take a single beer
    Given 100 bottles of beer on the wall
    When a bottle is taken down
    Then there are 99 bottles of beer on the wall

  Scenario: Can take multiple beers
    Given 100 bottles of beer on the wall
    When 5 bottles are taken down
    Then there are 95 bottles of beer on the wall

  Scenario: Ghosts can drink
    Given 100 bottles of beer on the wall
    And there is nobody in the room
    When 5 bottles are taken down
    And they are floating in the air
    Then there are 95 bottles of beer on the wall
    And there are ghosts in the room
```

``` javascript
var fs = require('fs');
var gherk = require('gherk');
var file = fs.readFileSync('drink.feature');

gherk.parse(file.toString());

// =>

[
  {
    feature: 'Can drink beer when thirsty',
    perspective: 'drinker',
    desire: 'to take beer off the wall',
    reason: 'to satisfy my thirst',
    scenarios: [
      {
        scenario: 'Can take a single beer',
        given: [
          '100 bottles of beer on the wall'
        ],
        when: [
          'a bottle is taken down'
        ],
        then: [
          'there are 99 bottles of beer on the wall'
        ]
      },
      {
        scenario: 'Can take multiple beers',
        given: [
          '100 bottles of beer on the wall'
        ],
        when: [
          '5 bottles are taken down'
        ],
        then: [
          'there are 95 bottles of beer on the wall'
        ]
      },
      {
        scenario: 'Ghosts can drink',
        given: [
          '100 bottles of beer on the wall',
          'there is nobody in the room'
        ],
        when: [
          '5 bottles are taken down',
          'they are floating in the air'
        ],
        then: [
          'there are 95 bottles of beer on the wall',
          'there are ghosts in the room'
        ]
      }
    ]
  }
]
```
