### 5 Steps to design any system
- Requirements Analysis 
  -
  - Functional Requirements
    - User can create tinyurl - with random url or with custom unique string
    - User can set expiration date for generated random link
    - any tinyurl should be redirected to original link
    - User can know how many times alink is clicked  
    - User can delete his tiny-urls
        

  - Non-Functional Requirements
    - High Availability
    - Low Latency 
    - Scalable


- Api Design
  - 
  - createUser(name:string, email:string): userObject
  - authGuarded - createTinyUrl(originalLink: string, customSlug: string = null, expirationDate: Date = null):Bool 
  - getOriginalUrl(tinyUrl): string
  - authGuarded - deleteUrl(tinyUrl: string): void
  - authGuarded - getHitCount(tinyUrl: string): number
  
 
  

- Define Data Model - db structure
  - User Table
    - UserId (int) - PK
    - Name (varchar)
    - Email (varchar)
    - CreatedAt (Date)
  - TinyUrls Table
    - UrlSlug (varchar) - PK
    - OriginalUrl (varchar)
    - UserId (int)
    - HistCount (int)
    - CreatedAt (Date)
    - ExpiredAt (Date) - Nullable


- High Level Design 
  - 
  - The system will generate the unique url slug by using
  - hash(randomNumber(5 digits) concat timestamps)
  - we can use bloom filter also to check the if slug is unique or not


- Scale up
  - Load Balancer with multiple read servers
  - Replication
  - Cashing
    - the system can cash the most visited links at our system
  - Sharding
    - Shard by consistency hashing at the original link
  


