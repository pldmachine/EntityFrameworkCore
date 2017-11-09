# EntityFrameworkCore

#What is new i EF Core?
- Support of non-relational databases

## Query lifecycle preview:

``csharp

 var book = new Book();
                 book.Description = "Sdfsdf";
                 book.Title = "Sdfsd";
                 context.Books.Add(book);
                 context.SaveChanges();
                 
                 ``
