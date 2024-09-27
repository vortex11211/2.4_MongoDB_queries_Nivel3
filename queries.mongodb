use('negocios')
//1.	Escriu una consulta per mostrar tots els documents en la col·lecció Restaurants
db.restaurantes.find({});
//2.	Escriu una consulta per mostrar el restaurant_id, name, borough i cuisine de tots els documents en la col·lecció Restaurants.
db.restaurantes.find({},{restaurant_id:1,name:1,borough:1,cuisine:1});
//3.	Escriu una consulta per mostrar el restaurant_id, name, borough i cuisine, però excloent el camp _id per tots els documents en la col·lecció Restaurants.
db.restaurantes.find({},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1});
//4.	Escriu una consulta per mostrar restaurant_id, name, borough i zip code, però excloent el camp _id per tots els documents en la col·lecció Restaurants
db.restaurantes.find({},{_id:0,restaurant_id:1,name:1,borough:1,"address.zipcode":1});
//5.	Escriu una consulta per mostrar tots els restaurants que estan en el Bronx.
db.restaurantes.find({borough:"Bronx"},{_id:0,restaurant_id:1,name:1,borough:1});
//6.	Escriu una consulta per mostrar els primers 5 restaurants que estan en el Bronx.
db.restaurantes.find({borough:"Bronx"},{_id:0,restaurant_id:1,name:1,borough:1}).limit(5);
//7.	Escriu una consulta per mostrar els 5 restaurants després de saltar els primers 5 que siguin del Bronx.
db.restaurantes.find({borough:"Bronx"},{_id:0,restaurant_id:1,name:1,borough:1}).skip(5).limit(5);
//8.	Escriu una consulta per trobar els restaurants que tenen algun score més gran de 90.
db.restaurantes.find({"grades.score":{$gt:90}},{_id:0,restaurant_id:1,name:1,borough:1,"grades.score":1});
//9.	Escriu una consulta per trobar els restaurants que tenen un score més gran que 80 però menys que 100.
db.restaurantes.find({"grades":{$elemMatch:{score:{$gt:80,$lt:100}}}},{_id:0,restaurant_id:1,name:1,borough:1,"grades.score":1});
//10.	Escriu una consulta per trobar els restaurants que estan situats en una longitud inferior a -95.754168.
db.restaurantes.find({"address.coord.0":{$lt:-95.754168}},{_id:0,restaurant_id:1,name:1,borough:1,"address.coord":1});
//11.	Escriu una consulta de MongoDB per a trobar els restaurants que no cuinen menjar 'American ' i tenen algun score superior a 70 i longitud inferior a -65.754168.
db.restaurantes.find({$and:[ {cuisine:{$ne:"American"}},{"grades.score":{$gt:70}},{"address.coord.0":{$lt:-65.754168}}]},{_id:0,name:1,cuisine:1,"grades.score":1,"address.coord":1});
//12.	Escriu una consulta per trobar els restaurants que no preparen menjar 'American' i tenen algun score superior a 70 i que, a més, es localitzen en longituds inferiors a -65.754168. Nota: Fes aquesta consulta sense utilitzar operador $and.
db.restaurantes.find({cuisine:{$ne:"American"},"grades.score":{$gt:70},"address.coord.0":{$lt:-65.754168}},{_id:0,name:1,cuisine:1,"grades.score":1,"address.coord":1});
//13.	Escriu una consulta per trobar els restaurants que no preparen menjar 'American ', tenen alguna nota 'A' i no pertanyen a Brooklyn. S'ha de mostrar el document segons la cuisine en ordre descendent.
db.restaurantes.find({cuisine:{$ne:"American"},borough:{$ne:"Brooklyn"},"grades.grade":"A"},{_id:0,name:1,cuisine:1,"grades.grade":1,borough:1}).sort({cuisine:-1});
//14.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que contenen 'Wil' en les tres primeres lletres en el seu nom.
db.restaurantes.find({name:/^Wil/i},{_id:0,name:1,borough:1,cuisine:1});
//15.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que contenen 'ces' en les últimes tres lletres en el seu nom.
db.restaurantes.find({name:/ces$/i},{_id:0,name:1,borough:1,cuisine:1});
//16.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que contenen 'Reg' en qualsevol lloc del seu nom.
db.restaurantes.find({name:/Reg/i},{_id:0,name:1,borough:1,cuisine:1});
//17.	Escriu una consulta per trobar els restaurants que pertanyen al Bronx i preparen plats Americans o xinesos.
db.restaurantes.find({borough:"Bronx", $or:[{cuisine:"American"},{cuisine:"Chinese"}]},{_id:0,name:1,cuisine:1,borough:1});
//18.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per aquells restaurants que pertanyen a Staten Island, Queens, Bronx o Brooklyn.
db.restaurantes.find({$or:[{borough:"Staten Island"},{borough:"Queens"},{borough:"Bronx"},{borough:"Brooklyn"}]},{_id:0,restaurant_id:1,name:1,cuisine:1,borough:1});
//19.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que NO pertanyen a Staten Island, Queens, Bronx o Brooklyn.
db.restaurantes.find({$nor:[{borough:"Staten Island"},{borough:"Queens"},{borough:"Bronx"},{borough:"Brooklyn"}]},{_id:0,restaurant_id:1,name:1,cuisine:1,borough:1});
//20.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que aconsegueixin una nota menor que 10.
db.restaurantes.find({"grades.score":{$lt:10}},{_id:0,restaurant_id:1,name:1,cuisine:1,borough:1,"grades.score":1});
//21.	Escriu una consulta per trobar el restaurant_id, name, borough i cuisine per a aquells restaurants que preparen marisc ('seafood') excepte si són 'American ', 'Chinese' o el name del restaurant comença amb lletres 'Wil'.
db.restaurantes.find({cuisine:"Seafood", $nor:[{cuisine:"American"},{cuisine:"Chinese"},{name:/^Wil/i}]},{_id:0,restaurant_id:1,name:1,cuisine:1,borough:1});
//22.	Escriu una consulta per trobar el restaurant_id, name i grades per a aquells restaurants que aconsegueixin un grade de "A" i un score d'11 amb un ISODate "2014-08-11T00:00:00Z",'
db.restaurantes.find({grades:{$elemMatch:{grade:"A",score:11,date:ISODate("2014-08-11T00:00:00Z")}}},{_id:0,restaurant_id:1,name:1,grades:1});
//23.	nt de l'array de graus conté un grade de "A" i un score 9 amb un ISODate "2014-08-11T00:00:00Z".
db.restaurantes.find({"grades.1.grade":"A","grades.1.score":9,"grades.1.date":ISODate("2014-08-11T00:00:00Z")},{_id:0,restaurant_id:1,name:1,"grades":1})
//24.	Escriu una consulta per trobar el restaurant_id, name, adreça i ubicació geogràfica per a aquells restaurants on el segon element de l'array coord conté un valor entre 42 i 52.
db.restaurantes.find({"address.coord.1":{$lt:52,$gt:42}},{_id:0,restaurant_id:1,name:1,"address.coord":1})
//25.	Escriu una consulta per organitzar els restaurants per nom en ordre ascendent.
db.restaurantes.find({},{_id:0,name:1}).sort({name:1});
//26.	Escriu una consulta per organitzar els restaurants per nom en ordre descendent.
db.restaurantes.find({},{_id:0,name:1}).sort({name:-1});
//27.	Escriu una consulta per organitzar els restaurants pel nom de la cuisine en ordre ascendent i pel barri en ordre descendent.
db.restaurantes.find({},{_id:0,name:1,cuisine:1,borough:1}).sort({cuisine:1,borough:-1});
//28.	Escriu una consulta per saber si les direccions contenen el carrer.
db.restaurantes.find({"address.street":{$exists:true}},{_id:0,name:1,"address.street":1});
//29.	Escriu una consulta que seleccioni tots els documents en la col·lecció de restaurants on els valors del camp coord és de tipus Double.
db.restaurantes.find({"address.coord":{$type:"double"}},{_id:0,name:1,"address.coord":1})
//30.	Escriu una consulta que seleccioni el restaurant_id, name i grade per a aquells restaurants que retornen 0 com a residu després de dividir algun dels seus score per 7.
db.restaurantes.find({"grades.score":{$mod:[7,0]}},{_id:0,name:1,restaurant_id:1,grades:1})
//31.	Escriu una consulta per trobar el name de restaurant, borough, longitud, latitud i cuisine per a aquells restaurants que contenen 'mon' en algun lloc del seu name.
db.restaurantes.find({name:/mon/i},{_id:0,name:1,borough:1,"address.coord":1,cuisine:1})
//32.	Escriu una consulta per trobar el name de restaurant, borough, longitud, latitud i cuisine per a aquells restaurants que contenen 'Mad' com a primeres tres lletres del seu name.*/
db.restaurantes.find({name:/^Mad/i},{_id:0,name:1,borough:1,"address.coord":1,cuisine:1})










