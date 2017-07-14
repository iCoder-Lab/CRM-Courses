# CRM-Courses

## Server side notes

* upload news to existing News oby its ID, sent base64 data. return then url of image. 
NewsUploadPhoto

* after addStudent request you create student and generate promoCode for him. This promoCode then should be send to User's email. 



# POST Requests

   * /addTeacher (Teacher) -> ErrorMessage
   * /addStudent (Student) -> ErrorMessage
   * /addCourse (Course) -> ErrorMessage
   * /addClass (Class) -> ErrorMessage
   * /addNews (News) -> ErrorMessage
   * /adminNotificate (AdminNotification) -> ErrorMessage
   * /teacherNotificate (TeacherNotification) -> ErrorMessage
   * /addHomework (Homework) -> ErrorMessage
   * /submitHomeWork (HomeworkSubmition) -> ErrorMessage 
   * /approveStudentAttandence (QrCode) -> ErrorMessage
   * /activatePromoCode (PromoCode) -> Student +  ErrorMessage
   * /setStudentNewAuth (StudentAuthCredentials) -> ErrorMessage
   
   ### metadata
   
   //We should try this inidividually
   * /uploadHomeworkImage/{HomeworkSubmitionId} -> ErrorMessage
   * /uploadNewsImage/{newsId} -> ErrorMessage
   
# GET Requests

   * /getNews -> Array < News >
   * /getCourses -> Array < Course >
   * /getClasses -> Array < Class >
   * /getStudentsInClass/{classId} -> Array < Student >
   * /getStudentAttandace/{studentId} -> Array < Attandance >
   * /getHomeworks/{classId} -> Array < HomeWork >
   * /getAllTeachers -> Array <Teacher>
   * /getHomeworkSubmissions/{homeworkId} -> Array <HomeworkSubmition>
   
   ### metadata 
   * /getStudentQrCode -> ??? Image encopded in base64 need for test 
      
   
# Models: 

### Teacher
    "id": Int,
    "name": String,
    "surname": String,
    "middleName": String
    "birthDate": String,
    "education": String,
    "awards": String,
    "startWorkingDate": String, //timestamp 
    "mobilePhone": String,  //0XXXyyyyyy
    "email": String, 
    "about" : String,

### Student
    "id": String,
    "name": String,
    "surname": String,
    "mobilePhone": String  //0XXXyyyyyy
    "email": String, 
    "classId": Int

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
    "price": Int,
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
    
    
### QrCode 
    "qrcode" : String // this string includes encription of data: StudentId, ClassId, currentTime released on server side
    
### HomeworkSubmition   
    "id": Int,
    "homeworkId": Int,
    "studentId": String,
    "classId": Int
    "title": String,
    "description": String
    "imagePath": String //only fot get methods
    //upload photo by homeworkSubmissionId 
    
### Attandance
    "studentId": Int,
    "classId": Int,
    "datetime" : String,
    "isAttended" : Bool
    
### AdminNotification

    "title": Stirng,
    "description" : String,
    "isToTeachers": Bool,
    "isToStudents": Bool,
    "isToGuests": Bool
    
### TeacherNotification 

    "classId": Int
    "title": String,
    "description": String
    
### PasswordReset 
    "login" : String,
    "oldPassword": String,
    "newPassword": String,
    "deviceId": String
    
### StudentAuthCredentials
    "studentId": Int,
    "login": String, //check for existing login
    "password": string,
    
### PromoCode 
    "promocode" : String
    "deviceId" : Stirng
    
### ErrorMessage
    "error": String
    
    
