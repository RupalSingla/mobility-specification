# Cancellation Terms

Example 1

Defifnition: Free cancellation until 15 minutes after the creation of the booking. No refund is provided after the start time.

```
cancellation_terms:
 
[
    {   
            "cancel_by":{
		"label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065"
                },
                "duration":{
                  PT15M
                }
        }
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		"label": "Schedule Rides"
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065Z"
                }
        }
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            },  
  ]

```

Example 2

Defifnition: Free cancellation up to 1 hour before the start time. No refund is provided after 1 hour before the start time.

```
cancellation_terms:
  [
    {
              "cancel_by":{
                "range":{
                    "end":"2023-08-23T10:29:00.065"
                    },
                 "duration":"PT1H"
                },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
               
              
            },
    {
              "cancel_by":{
                "range":{
                    "end": "2023-08-23T10:35:00.065"
                },
                 "duration":"PT1H"
                },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            }  
  ]
```

Example 3

Defifnition: Free cancellation up until 6 hours before the start time.From 6 hours to 1 hour before the start time, there is a penalty of 50% of the booking amount or Rs 1000, whichever is lower.
No refund is provided after 1 hour before the start time.

```
cancellation_terms:
  [
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
                "label": "Free cancellation up until 6 hours before the start time",
                "range":{
                    "start": "2023-08-23T11:30:00.065",
                    "end": "2023-08-23T04:30:00.065"
                },
                "duration":"PT6H"
                },
        
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
                "label": "Penalty From 6 hours to 1 hour before the start time",
                "range":{
                    "start": "2023-08-23T11:30:00.065",
                    "end": "2023-08-23T08:30:00.065"
                },
                "duration":"PT1H"
        },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "50",
                "amount": "1000"
              }
            }  
  ]
```
Example 4

Defifnition: Free cancellation until 30 minutes after the creation of the booking. No refund is provided after that point.

```
cancellation_terms:
 
[
    {   
            "cancel_by":{
		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065"
                },
                "duration": "PT30M"
                },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		"label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065Z"
                }
        },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            }  
  ]
```
Example 5

Defifnition: Free cancellation up until the start time of the booking. No refund is provided after the start time.

```
cancellation_terms:
 
[
    {   
            "cancel_by":{
		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065",
                    "end":
                      "2023-08-23T11:29:00.065"  
                }
            },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:31:00.065Z"
                }
              },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            } 
  ]

```

Example 6

Defifnition: Free cancellation up to 1 hour before the start time.
From 1 hour before the start time to the start time, there is a penalty of 100% of the booking amount or Rs 1000, whichever is lower.
No refund is provided after the start time.

```
cancellation_terms:
 
[
    {   
            "cancel_by":{
		        "label": "Schedule Rides",
                "range":{
                    "end":
                      "2023-08-23T10:29:00.065"  
                },
                "duration":"PT1H"
                
        },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
     {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065Z",
                     "end":
                      "2023-08-23T10:30:00.065Z"  
                }
              },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100",
                "amount": "1000"
              }
            },        
    {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:31:00.065Z"
                }
              },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            }
  ]

```

Example 7

Defifnition: Free cancellation up to 1 hour before the start time.
From 1 hour before the start time to the start time, there is a penalty of 50% of the booking amount or Rs 1000, whichever is lower.
No refund is provided after 1 hour before the start time.

```
cancellation_terms:
 
[
    {   
            "cancel_by":{
		        "label": "Schedule Rides",
                "range":{
                    "end":
                      "2023-08-23T10:29:00.065"  
                },
                "duration":"PT1H"
                
        },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "0"
              }
            },
     {
              "fulfillment_state": {
                "descriptor": {
                  "code": "RIDE_STARTED"
                }
              },
              "cancel_by":{
  		        "label": "Schedule Rides",
                "range":{
                    "start":
                      "2023-08-23T11:30:00.065Z",
                     "end":
                      "2023-08-23T10:30:00.065Z"  
                }
              },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "50",
                "amount": "1000"
              }
            },        
    {
              "cancel_by":{
  		        "label": "Schedule Rides",
                "range":{
                    "end":
                      "2023-08-23T11:00:00.065Z"
                }
              },
              "reason_required": true,
              "cancellation_fee": {
                "percentage": "100"
              }
            }
  ]

```
