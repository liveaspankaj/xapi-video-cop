# Templates

The following template statements are provided for your convenience and conform to the video profile requirements.

## Initialized

```
{
    "actor": {
        "mbox": "mailto:jlh@example.com",
        "name": "Video User",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/initialized",
        "display": {
            "en-US": "initialized"
        }
    },
    "timestamp": "2018-08-07T15:27:52.365Z",
    "object": {
        "definition": {
            "type": "https://w3id.org/xapi/video/activity-type/video",
            "name": {
                "en-US": "Ocean Life"
            },
            "description": {
                "en-US": "A short video clip of ocean lifeforms, used by videojs.com as part of their demo."
            }
        },
        "id": "http://vjs.zencdn.net/v/oceans.mp4",
        "objectType": "Activity"
    },
    "context": {
        "contextActivities": {
            "category": [
                {
                    "id": "https://w3id.org/xapi/video"
                }
            ]
        },
        "extensions": {
            "https://w3id.org/xapi/video/extensions/volume": 1,
            "https://w3id.org/xapi/video/extensions/video-playback-size": "640x264",
            "https://w3id.org/xapi/video/extensions/user-agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.84 Safari/537.36",
            "https://w3id.org/xapi/video/extensions/speed": "1x",
            "https://w3id.org/xapi/video/extensions/cc-subtitle-lang": "",
            "https://w3id.org/xapi/video/extensions/completion-threshold": "1.0",
            "https://w3id.org/xapi/video/extensions/session-id": "86c5b148-4462-4da9-a13f-b570c27fa049",
            "https://w3id.org/xapi/video/extensions/length": 46.613333,
            "https://w3id.org/xapi/video/extensions/quality": "960x400",
            "https://w3id.org/xapi/video/extensions/screen-size": "2560x1440",
            "https://w3id.org/xapi/video/extensions/frame-rate": "23.98",
            "https://w3id.org/xapi/video/extensions/cc-enabled": false,
            "https://w3id.org/xapi/video/extensions/full-screen": false
        },
        "registration": "96094a33-cc66-4d9a-8810-a0850ae2a4e1"
    },
    "id": "86c5b148-4462-4da9-a13f-b570c27fa049"
}
```

## Played

```
var playedStmt = {
  "actor": actor,
  "verb": {
    "id": "https://w3id.org/xapi/video/verbs/played",
    "display": {
      "en-US": "played"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time": resultExtTime,
    }
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/session-id": sessionID

    }
  },
};
```

## Paused

```
var pausedStmt = {
  "actor": actor,
  "verb": {
    "id": "https://w3id.org/xapi/video/verbs/paused",
    "display": {
      "en-US": "paused"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time": resultExtTime,
      "https://w3id.org/xapi/video/extensions/progress": progress,
      "https://w3id.org/xapi/video/extensions/played-segments": played_segments
    }
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/session-id": sessionID

    }
  },
};
```

## Seeked

```
var seekedStmt = {
  "actor": actor,
  "verb": {
    "id": "https://w3id.org/xapi/video/verbs/seeked",
    "display": {
      "en-US": "seeked"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time-from": seekStart,
      "https://w3id.org/xapi/video/extensions/time-to": currentTime
    }
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/session-id": sessionID

    }
  },
};
```

## Interacted

```
var interactedStatement = {
  "actor": actor,
  "verb": {
    "id": "http://adlnet.gov/expapi/verbs/interacted",
    "display": {
      "en-US": "interacted"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time": resultExtTime
    }
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/full-screen": fullScreenOrNot,
      "https://w3id.org/xapi/video/extensions/screen-size": screenSize,
      "https://w3id.org/xapi/video/extensions/video-playback-size": playbackSize,
      "https://w3id.org/xapi/video/extensions/quality": quality,
      "https://w3id.org/xapi/video/extensions/cc-enabled": ccEnabled,
      "https://w3id.org/xapi/video/extensions/cc-subtitle-lang": ccLanguage,
      "https://w3id.org/xapi/video/extensions/speed": playbackRate + "x",
      "https://w3id.org/xapi/video/extensions/user-agent": userAgent,
      "https://w3id.org/xapi/video/extensions/volume": volume,
      "https://w3id.org/xapi/video/extensions/session-id": sessionID
    }
  },
};
```

## Completed

```
var completedStmt = {
  "actor": actor,
  "verb": {
    "id": "http://adlnet.gov/expapi/verbs/completed",
    "display": {
      "en-US": "completed"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time": currentTime,
      "https://w3id.org/xapi/video/extensions/progress": progress
    },
    "completion" : boolean,
    "duration" : lengthOfVideo
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/session-id": sessionID

    }
  },
};
```

## Terminated

```
var terminatedStmt = {
  "actor": actor,
  "verb": {
    "id": "http://adlnet.gov/expapi/verbs/terminated",
    "display": {
      "en-US": "terminated"
    }
  },
  "object": {
    "id": objectID,
    "definition": {
      "name": {
        "en-US": activityTitle
      },
      "description": {
        "en-US": activityDesc
      },
      "type": "https://w3id.org/xapi/video/activity-type/video"
    },
    "objectType": "Activity"
  },
  "result": {
    "extensions": {
      "https://w3id.org/xapi/video/extensions/time": currentTime,
      "https://w3id.org/xapi/video/extensions/progress": progress
    }
  },
  "context": {
    "contextActivities": {
      "category": [{
        "id": "https://w3id.org/xapi/video"
      }]
    },
    "extensions": {
      "https://w3id.org/xapi/video/extensions/session-id": sessionID

    }
  },
};
```



