# Templates

The following template statements are provided for your convenience and conform to the video profile requirements.

## Initialized

```
var initializedStmt = {
  "id": sessionID,
  "actor": actor,
  "verb": {
    "id": "http://adlnet.gov/expapi/verbs/initialized",
    "display": {
      "en-US": "initialized"
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
      "https://w3id.org/xapi/video/extensions/session-id": sessionID,
      "https://w3id.org/xapi/video/extensions/cc-enabled": ccEnabled,
      "https://w3id.org/xapi/video/extensions/cc-subtitle-lang": ccLanguage,
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
    "success" : boolean,
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



