# programscheduler
A shia event management application.

## Events

### Metadata
An event *must* have the following metadata, at least:
```javascript
{
  title: 'Ashura majlis',                // String
  author: 3253523634                     // Int
  desc: 'Sample description',            // String
  public: true,                          // Boolean
  type: 321,                             // Int - mapped to type of events list
  audience: 'f',                         // String - f|m|b (female, male, both)
  location: {                            // Object
    city: 'Brampton',                    // String
    province: 'ON',                      // String
    country: 'Canada',                   // String
    postal: 'A1A1A1'                     // String
  },
  date: '2005-09-16T23:59:58.75',        // String - UTC timestamp
  dateCreated: '2004-09-16T23:59:58.75'  // String - UTC timestamp
}
```

### Types of events
The application should be able to create/manage various different types of events. Some of which are:
- majlis
- niyaz
- jashan
- juloos
- dua

We can add flexibility of adding an 'other' field but the event type might be meaningless if users are able to enter any arbitrary text (ie. niaz vs niyyaz vs niyaz). To counter this, we can do the following:
* add synonym functionality -- the application will know niyaz = niaz = niyyaz (preferred)
* add functionality for the user to add new entry in 'types of events' which will be available globally

```javascript
[{
  id: 321
  name: 'Majlis'
}, {
  id: 432,          // unique identifier
  name: 'Niyaz',    // name of type of event
  syn: [            // synonyms can go in here
    'Niaz',
    'Niyyaz'
  ]
}, {
  id: 548,
  name: 'Jashan'
}, {
  id: 932,
  name: 'Juloos'
}]
```

### Authentication
Authentication is not required to view an event; however, it is required to create and RSVP to events.

#### Registration, Login, Reset Password, Activation
Should be streamlined via [firebase](https://www.firebase.com/).

---

1)  Majlis / Niyaz / Jashan / Milad & Others

Different categories
public / private
gents / ladies / both

2) Sign Up / Login

Sign up using email - phase 1 
Sign up using twitter / facebook - phase 2

Login / using email & password
Edit your program while signed in

3) Event Pages

Single event pages
Social Media Sharing

4) Program Details

Event Name
Event Date
Event Address
Event Phone Number
Event Category
Event 