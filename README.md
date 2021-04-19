# Python Django API with GraphQL


python manage.py makemigrations

python manage.py migrate

data.json file saved in the current directory, 

# run the next command  to import the data into the database:

python manage.py loaddata db.json

Installed 5 object(s) from 1 fixture(s)

5 models in file .json

python manage.py runserver


http://127.0.0.1:8000/graphql

query {

	allBooks {
	
		id
		
		title
		
		author
		
		yearPublished
		
		review
		
	}
	
}

# or

query {

  allBooks {
  
    id
    
    title
    
    author
    
  }
  
}

# or

query {

  book(bookId: 2) {
  
    id
    
    title
    
    author
    
  }
  
}

# Creating a book

mutation createMutation {

  createBook(bookData: {title: "Things Apart", author: "Chinua Achebe", yearPublished: "1985", review: 3}) {
  
    book {
    
      title,
      
      author,
      
      yearPublished,
      
      review
      
    }
    
  }
  
}

# result :

{

  "data": {
  
    "createBook": {
    
      "book": {
      
        "title": "Things Apart",
	
        "author": "Chinua Achebe",
	
        "yearPublished": "1985",
	
        "review": 3
	
      }
      
    }
    
  }
  
}

# Updating an existing book

mutation updateMutation {

  updateBook(id: 5, bookData: {title: "Things Fall Apart", author: "Chinua Achebe", yearPublished: "1958", review: 5}) {
  
    book {
    
      title,
      
      author,
      
      yearPublished,
      
      review
      
    }
    
  }
  
}


# Deleting a book

mutation deleteMutation{

  deleteBook(id: 7) {
  
    book {
    
      id
      
    } 
    
  }
  
}

# result

{

  "data": {
  
    "deleteBook": null
    
  }
  
}


Note:

mutations

https://www.apollographql.com/docs/tutorial/mutations/


