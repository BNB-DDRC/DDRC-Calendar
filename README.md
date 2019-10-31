# siestaNbrekkie Calendar Reservation
Reservation and lodging information microservice for a hotel reservation web application

## Related Projects
  - https://github.com/siestaNbrekkie/reviews
  - https://github.com/siestaNbrekkie/image-carousel
  - https://github.com/siestaNbrekkie/image-carousel/reservations

## Table of Contents
1. [Usage](#Usage)
1. [Requirements](#requirements)
1. [Development](#development)

## Requirements
- Node v8.15.x
- MySQL v5.7.x
- npm v6.10.x
- docker

### Installing Dependencies
From within the root directory

1. Install project dependencies
```javascript
npm install
```

2. Create MySQL Database
```javascript
npm run db
```

3. Seed MySQL Database
```javascript
npm run seed-data
```

4. Build the microservice bundle
```javascript
npm run build
```

5. To start the server
```javascript
npm run server
```

6. Go to to see the component `localhost:3004/rooms/1`


# calendar

## API

#### URL

`/rooms/:id`

#### GET:

`/room/:id/availability` - Retrieves the current available and unavailable dates for this location ID in body of GET request

              ex: {id: number}

#### PATCH:

`room/:id/availability` - Updates this location's available dates based on the dates chosen on the calendar, dates chosen will be sent in PATCH body

              ex: {dateStart: date, dateEnd: date}

#### POST:

`/room/` - Adds new location passing information that is needed in POST body, ID given by database

           ex: {sundayMin: number, mondayMin: number, tuesdayMin: number, wednesdayMin: number, thursdayMin: number, fridayMin: number, saturdayMin: number, maxDays: number, unavailableDates: dates}

#### DELETE:

`room/:id` - Removes the location by ID given from the database