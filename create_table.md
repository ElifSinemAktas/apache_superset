  ```shell
  create table users(
      userid integer not null primary key,
      username char(8),
      firstname varchar(30),
      lastname varchar(30),
      city varchar(30),
      state char(2),
      email varchar(100),
      phone char(14),
      likesports boolean,
      liketheatre boolean,
      likeconcerts boolean,
      likejazz boolean,
      likeclassical boolean,
      likeopera boolean,
      likerock boolean,
      likevegas boolean,
      likebroadway boolean,
      likemusicals boolean);
  ```
  
  ```shell
  create table venue(
      venueid smallint not null primary key,
      venuename varchar(100),
      venuecity varchar(30),
      venuestate char(2),
      venueseats integer);
  ```
  
  ```shell
  create table category(
      catid smallint not null primary key,
      catgroup varchar(10),
      catname varchar(10),
      catdesc varchar(50));
  ```
  
  ```shell
  create table date(
      dateid smallint not null primary key,
      caldate date not null,
      day character(3) not null,
      week smallint not null,
      month character(5) not null,
      qtr character(5) not null,
      year smallint not null,
      holiday boolean default('N'));
  ```
  ```shell
  create table event(
      eventid integer not null primary key,
      venueid smallint not null,
      catid smallint not null,
      dateid smallint not null,
      eventname varchar(200),
      starttime timestamp);
  ```
  ```shell
  create table listing(
      listid integer not null primary key,
      sellerid integer not null,
      eventid integer not null,
      dateid smallint not null,
      numtickets smallint not null,
      priceperticket decimal(8,2),
      totalprice decimal(8,2),
      listtime timestamp);
  ```
  
  ```shell
  create table sales(
      salesid integer not null primary key,
      listid integer not null ,
      sellerid integer not null,
      buyerid integer not null,
      eventid integer not null,
      dateid smallint not null ,
      qtysold smallint not null,
      pricepaid decimal(8,2),
      commission decimal(8,2),
      saletime timestamp);
  ```