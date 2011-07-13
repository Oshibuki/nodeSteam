# node-steam

A [node.js](http://github.com/joyent/node) wrapper for Valve's [Steam Web API](http://developer.valvesoftware.com/wiki/Steam_Web_API).  Also supports the methods provided for [TF2/TF2Beta/Portal](http://wiki.teamfortress.com/wiki/WebAPI).

## Installation

  npm install steam
  

### Methods

  Note that all methods accept a single options object.  The key names match the query string parameters specified in the valve documentation. (additional docs coming soon.  For now, see usage and the valve documenation for any questions)

####getNewsForApp


####getGlobalAchievementPercentagesForApp


####getPlayerSummaries


####getSchema


####getPlayerItems


## Usage

    var steam = require('steam');
    
    var s = new steam({
      apiKey: 'XXXXXXXXXXXXXXXX',
      format: 'json' //optional
    });
    s.getNewsForApp({
      appid: 440,
      count: 3,
      maxlength: 300,
      callback: function(data) {
        console.log(data);
      }
    })
    s.getGlobalAchievementPercentagesForApp({
      gameid: 440,
      callback: function(data) {
        console.log(data);
      }
    });
    s.getPlayerSummaries({
      steamids: ['76561198037414410', '76561197960435530'],
      callback: function(data) {
        console.log(data);
      }
    })
    s.getSchema({
      gameid: 440,
      callback: function(data) {
        console.log(data);
      }
    })
    s.getPlayerItems({
      gameid: 440,
      steamid: '76561197960435530',
      callback: function(data) {
        console.log(data);
      }
    })