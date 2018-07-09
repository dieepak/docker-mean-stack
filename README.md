# Docker + MEAN Stack

###APIs Call
                    
Method  | URL | Action
------------- | ------------- | -------------
GET  | /api/hotels | Get all/multiple hotels
POST  | /api/hotels/ | Create new hotel
GET  | /api/hotels/12345 | Get a specific hotel
PUT  | /api/hotels/12345 | Update a specific hotel
DELETE  | /api/hotels/12345 | Delete a specific hotel

Method  | URL | Action
------------- | ------------- | -------------
GET  | /api/hotels/12345/reviews | Get all reviews for a specific hotel
POST  | /api/hotels/12345/reviews | Add a new review for a specific hotel
GET  | /api/hotels/12345/reviews/54321 | Get a specific review for a specific hotel
PUT  | /api/hotels/12345/reviews/54321 | Update a specific review for a specific hotel
DELETE  | /api/hotels/12345/reviews/54321 | Delete a specific review for a specific hotel


### Stack deployment

![](https://dieepak.github.io/assets/docker-mean-mongo-update.png)


###Update sub-document (reviews) with id

    $ mongo

	>  use meanhotel
	switched to db meanhotel

	> db.hotels.update(
	    {},
 	   {
        $set : {
            'reviews.0._id' : ObjectId()
      		  }
		},
		{
			multi : true
		}
	)

	WriteResult({ "nMatched" : 12, "nUpserted" : 0, "nModified" : 12 })


    