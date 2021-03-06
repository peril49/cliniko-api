Attendees
============

**Deprecation warning**: attendees return a deprecated link for `appointment`. You should instead use `booking`. The `appointment` link returns a 404 when linking to group bookings. The `appointment` link will be removed in February 2017.

* [Get Attendees](#get-attendees "This will return all attendees.")
* [Get Deleted Attendees](#get-deleted-attendees "This will return all deleted attendees")
* [Get Cancelled Attendees](#get-cancelled-attendees "This will return all cancelled attendees")
* [Get Attendee](#get-attendee "This will return a specified attendee.")
* [Create Attendee](#create-attendee "This will create an attendee.")
* [Update Attendee](#update-attendee "This will update an attendee.")
* [Delete Attendee](#delete-attendee "This will delete an attendee.")

Get Attendees
----------------

**Resources**
* ```GET /attendees``` get all attendees
* ```GET /group_appointments/:id/attendees``` get all attendees for a specified group appointment
* ```GET /individual_appointments/:id/attendees``` get all attendees for a specified individual appointment


**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "attendees": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-06-28T21:33:26Z",
      "arrived": null,
      "booking_ip_address": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": null,
      "cancelled_at": null,
      "booking": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/bookings/1"
        }
      },
      "patient": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/patients/82"
        }
      },
      "invoices": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
        }
      },
      "links": {
        "self": "http://local.cliniko.dev:3000/v1/attendees/1"
      }
    }
  ],
  "total_entries": 2037,
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees?page=1",
    "next": "http://local.cliniko.dev:3000/v1/attendees?page=2"
  }
}
```

Get Deleted Attendees
----------------

**Resources**
* ```GET /attendees/deleted``` get all deleted attendees
* ```GET /group_appointments/:id/attendees``` get all deleted attendees for a specified group appointment
* ```GET /individual_appointments/:id/attendees``` get all deleted attendees for a specified individual appointment

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "attendees": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-06-28T21:33:26Z",
      "arrived": null,
      "booking_ip_address": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": "2016-06-28T21:33:26Z",
      "cancelled_at": null,
      "booking": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/bookings/1"
        }
      },
      "patient": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/patients/82"
        }
      },
      "invoices": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
        }
      },
      "links": {
        "self": "http://local.cliniko.dev:3000/v1/attendees/1"
      }
    }
  ],
  "total_entries": 143,
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees/deleted?page=1",
    "next": "http://local.cliniko.dev:3000/v1/attendees/deleted?page=2"
  }
}
```

Get Cancelled Attendees
----------------

**Resources**
* ```GET /attendees/cancelled``` get all cancelled attendees
* ```GET /group_appointments/:id/attendees``` get all cancelled attendees for a specified group appointment
* ```GET /individual_appointments/:id/attendees``` get all cancelled attendees for a specified individual appointment

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees/cancelled \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "attendees": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-06-28T21:33:26Z",
      "arrived": null,
      "booking_ip_address": null,
      "cancellation_note": "Last minute cancellation",
      "cancellation_reason": 50,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": null,
      "cancelled_at": null"2016-06-28T21:33:26Z",
      "booking": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/bookings/1"
        }
      },
      "patient": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/patients/82"
        }
      },
      "invoices": {
        "links": {
          "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
        }
      },
      "links": {
        "self": "http://local.cliniko.dev:3000/v1/attendees/1"
      }
    }
  ],
  "total_entries": 2037,
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees?page=1",
    "next": "http://local.cliniko.dev:3000/v1/attendees?page=2"
  }
}
```

Get Attendee
------------

**Resources**
* ```GET /attendees/:id``` get a specified attendee

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-06-28T21:33:26Z",
  "arrived": null,
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "cancelled_at": null,
  "booking": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/bookings/1"
    }
  },
  "patient": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/patients/82"
    }
  },
  "invoices": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
    }
  },
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees/1"
  }
}
```

Create Attendee
----------------
**Resources**
* ```POST /attendees``` create an attendee

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "appointment_id": "1", "patient_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.cliniko.com/attendees/1 }
```
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-06-28T21:33:26Z",
  "arrived": null,
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "cancelled_at": null,
  "booking": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/bookings/1"
    }
  },
  "patient": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/patients/82"
    }
  },
  "invoices": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
    }
  },
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees/1"
  }
}
```

Update Attendee
----------------
**Resources**
* ```PUT /attendees/:id``` update an attendee

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "arrived": true }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-06-28T21:33:26Z",
  "arrived": true,
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "cancelled_at": null,
  "booking": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/bookings/1"
    }
  },
  "patient": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/patients/82"
    }
  },
  "invoices": {
    "links": {
      "self": "http://local.cliniko.dev:3000/v1/attendees/1/invoices"
    }
  },
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/attendees/1"
  }
}
```

Delete Attendee
----------------
**Resources**
* ```DELETE /attendees/:id``` delete an attendee

**Example Request**
```shell
curl https://api.cliniko.com/v1/attendees/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Attendees
----------------

For any route that returns a set of attendees, you can filter them by:
* ```booking_id``` Integer
* ```created_at``` DateTime
* ```id``` Integer
* ```patient_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
