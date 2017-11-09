# EntityFrameworkCore

#What is new i EF Core?
- Support of non-relational databases

## Query lifecycle preview:

```csharp

var book = new Book();
book.Description = "Desc";
book.Title = "Title";
context.Books.Add(book);
context.SaveChanges();
                 
 ```

**result**: 

Opening connection to database 'EFInActionChapter1' on server '(local)'.
Opened connection to database 'EFInActionChapter1' on server '(local)'.
Beginning transaction with isolation level 'ReadCommitted'.
Executing DbCommand [Parameters=[@p0='?', @p1='?' (Size = 4000), @p2='?', @p3='?' (Size = 4000)], CommandType='Text', CommandTimeout='30']
SET NOCOUNT ON;
INSERT INTO [Books] ([AuthorId], [Description], [PublishedOn], [Title])
VALUES (@p0, @p1, @p2, @p3);
SELECT [BookId]
FROM [Books]
WHERE @@ROWCOUNT = 1 AND [BookId] = scope_identity();
Failed executing DbCommand (22ms) [Parameters=[@p0='?', @p1='?' (Size = 4000), @p2='?', @p3='?' (Size = 4000)], CommandType='Text', CommandTimeout='30']
SET NOCOUNT ON;
INSERT INTO [Books] ([AuthorId], [Description], [PublishedOn], [Title])
VALUES (@p0, @p1, @p2, @p3);
SELECT [BookId]
FROM [Books]
WHERE @@ROWCOUNT = 1 AND [BookId] = scope_identity();
Disposing transaction.
Closing connection to database 'EFInActionChapter1' on server '(local)'.
Closed connection to database 'EFInActionChapter1' on server '(local)'.
