# CRM-Courses

upload news to existing News oby its ID, sent base64 data. return then url of image. 
NewsUploadPhoto





# POST Requests

   * /addTeacher (Teacher)
   * /addStudent (Student)
   * /addCourse (Course)
   * /addClass (Class)
   * /addNews (News)
   * /adminNotificate (AdminNotification)
   * /teacherNotificate (TeacherNotification)
   * /addHomework (Homework)
   * /submitHomeWork (HomeworkSubmition) then upload image to HomeworkSubmitionId
   * /approveStudentAttandence
   
# GET Requests

   * /getNews -> Array < News >
   * /getCourses -> Array < Course >
   * /getClasses -> Array < Class >
   * /getStudentsInClass/{classId} -> Array < Student >
   * /getStudentAttandace/{studentId} -> Array < Attandance >
   * /getHomeworks/{classId} -> Array < HomeWork >
   * getAllTeachers -> Array <Teacher>
   
# Models: 

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
    "deviceId": String

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
    
    
### QrCode 
    "qrcode" : String
    
### HomeworkSubmition   
    "id": Int,
    "homeworkId": Int,
    "studentId": String,
    "classId": Int
    "title": String,
    "description": String
    
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
    
### StudentAttandance
    "code": String // this string includes encription of data: StudentId, ClassId, currentTime released on server side
