# CRM-Courses

upload news to existing News oby its ID, sent base64 data. return then url of image. 
NewsUploadPhoto

Models: 

### Teacher
    "id": Int,
    "name": String,
    "surname": String,
    "middleName": String
    "birthDate": String,
    "education": String,
    "awards": String,
    "startWorkingDate": String //timestamp 
    "mobilePhone": String  //0XXXyyyyyy
    "email": String 
    "about" : String

### Student
    "id": String,
    "name": String,
    "surname": String,
    "mobilePhone": String  //0XXXyyyyyy
    "email": String 
    "classId": Int //

### Course
    "id": Int
    "name": String,
    "description": String
### Class
    "id": Int
    "courseId": Int,
    "courseName": String,
    "description": String,
    "startDate": String,
    "endDate": String, 
    "teacherId": Int,
    "teacherName" : String,
    "price": String,
    "notes": String
    
### News 
    "id": Int,
    "title": String,
    "description": String,
    "publicationDate": String, //timestamp
    "endDate": String //timestamp
    "imagePath": String //only or GET request
    
        
### HomeWork
    "id": Int,
    "classId": Int,
    "title": Int,
    "description: String,
    
### HomeworkSubmition
### Attandance
### ChatGroup
### 
