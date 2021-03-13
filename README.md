# GO-GraphQL

### GraphQL with Golang ###
In this chapter of Full Cycle Course 2.0 was implemented an API with GraphQL, there are so many others chapters about communications how about REST and gRPC


### Playground instructions ###
The application is able to create a course, chapters, categories and also to consult your information. Below there are some querys and mutations to test it 

* findCategories

query findCategories{
  categories {
    id
    name
    description
    courses {
      name
    }
  }
}


* createCategory 

mutation createCategory{
    createCategory(input: {name: "PHP",description: "PHP is awesome"}){
        id
        name
        description
    }
}


* createCourse

mutation createCourse{
    createCourse(
        input: {
            name: "Evolving with PHP",
            description: "Mega PHP is awesome",
            categoryId: "T5577006791947779410"
        }
    ){
       id
       name
       description
       category{
           id
           name
       }
    }
}


* findCourses

query findCourses{
  courses{
    id
   	name
    description
    chapters{
      id
      name
    }
    category{
        id
        name
        description
    }
  }
}


* createChapter

mutation createChapter{
    createChapter(
        input: {
            name: "Evolving with PHP",
            courseId: "T8674665223082153551"
        }
    ){
       id
       name
       course{
           name
       }
    }
}
