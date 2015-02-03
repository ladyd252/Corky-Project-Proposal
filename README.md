# Corky

Heroku link coming soon!

## Minimum Viable Product
Corky is a picture sharing app for large events. It allows attendees to text pictures and/or messages to be displayed in a  real time updated slideshow. Users can:
- [ ] Register for an account
- [ ] Log in/out (sessions)
- [ ] Create events
- [ ] Navigate to their event page during an event and display on a screen viewable by guests.
- [ ] The event page will display a number for guests to send SMS and MMS.
- [ ] The event page will live update the slideshow on the screen as pictures and messages are received, sharing pictures and messages with all guests.


## Design Docs
* [View Wireframes][views]
* [DB schema][schema]

[views]: ./docs/views.md
[schema]: ./docs/db_schema.md

## Implementation Timeline

### Phase 1: User Authentication, Basic Events and Posts (~1 day)
I will implement user authentication in Rails based on the practices learned at
App Academy. I will also implement the API routes to serve event and post data as JSON.
As part of this phase, I will make my initial push to Heroku and ensure everything works as expected in production.

[Details][phase-one]

### Phase 2: First Backbone Views: Events (~1 day)
In this phase I will add Backbone models and collections that fetch data from those routes for events.
By the end of this phase, there will be backbone views for indexing a user's events, a new event form, and a show page for an event (which will be mostly empty at this point).

[Details][phase-two]

### Phase 3: Working with Twilio API to generate phone numbers  (~1 day)
In this phase I will start working the the Twilio API, which will provide a lot of the functionality in my app. I will be using the Twilio API to generate phone numbers for new events. This will be done by making a GET request to obtain a list of available numbers fitting any necessary parameters (such as an sms/mms enabled number) and a POST request to actually purchase a number from this list.

[Details][phase-three]

### Phase 4: Saving new messages/ picture URLs from text messages (~1 day)
In this phase I will start handling incoming texts to event phone numbers. I will save data from POST requests Twilio makes to my app to new instances of posts, which could optionally include body text and/or a picture url. Twilio hosts up to 5GB of media for free so I am currently not planning on saving the pictures somewhere else, but just accessing them using the URL provided in the HTTP request parameters by Twilio.

[Details][phase-four]

### Phase 5: Updating Event show page with pictures, picture transitions (~2 days)
In this phase I will update my event show page to include post subviews. I will also work on making a looping slideshow, and add nice picture transitions using jQuery, css, and html. Finally, I will have to make sure my backbone posts collection fetches in regular intervals (likely ~30seconds) so that new pictures in the database can be added to the event show page.

[Details][phase-five]


[phase-one]: ./docs/phases/phase1.md
[phase-two]: ./docs/phases/phase2.md
[phase-three]: ./docs/phases/phase3.md
[phase-four]: ./docs/phases/phase4.md
[phase-five]: ./docs/phases/phase5.md
