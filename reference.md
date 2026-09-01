# Reference
## Sessions
<details><summary><code>client.Sessions.ListSessions(AgentSlug, OwnerID) -> *funcateservergosdk.ListSessionsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List sessions for the specified agent and owner with optional pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.ListSessionsRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
    Sort: funcateservergosdk.String(
        "-created_at",
    ),
    Filter: funcateservergosdk.String(
        "(created_at>1732924800000)",
    ),
    Fields: funcateservergosdk.String(
        "id,agent_slug,owner_id,created_at",
    ),
}
client.Sessions.ListSessions(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — The page (aka. offset) of the paginated list (default to 1).
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `*int` — The max returned sessions per page (default to 30).
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Specify the ORDER BY fields. Add - / + (default) in front of the attribute for DESC / ASC order, e.g.: // DESC by created and ASC by name ?sort=-created_at
    
</dd>
</dl>

<dl>
<dd>

**filter:** `*string` 

Filter expression to filter/search the returned sessions list, e.g.: ?filter=(created_at>1732924800000)
The syntax basically follows the format OPERAND OPERATOR OPERAND, where: OPERAND - could be any field literal, string (single or double quoted), number, null, true, false OPERATOR - is one of: = Equal != NOT equal > Greater than >= Greater than or equal < Less than <= Less than or equal ~ Contains (for strings) !~ NOT contains (for strings) To group and combine several expressions you can use parenthesis (...), && (AND) and || (OR) tokens. Single line comments are also supported: // Example comment.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=id,agent_slug,owner_id,created_at
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.CreateSession(AgentSlug, OwnerID) -> *funcateservergosdk.CreateSessionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new session for the specified agent and owner
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.CreateSessionRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
}
client.Sessions.CreateSession(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.GetSession(AgentSlug, OwnerID, SessionID) -> *funcateservergosdk.GetSessionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve details of a specific session for an owner
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetSessionRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
    SessionID: "<SESSION_ID>",
}
client.Sessions.GetSession(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>

<dl>
<dd>

**sessionID:** `string` — Session identifier
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.DeleteSession(AgentSlug, OwnerID, SessionID) -> *funcateservergosdk.DeleteSessionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a specific session for an owner
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.DeleteSessionRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
    SessionID: "<SESSION_ID>",
}
client.Sessions.DeleteSession(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>

<dl>
<dd>

**sessionID:** `string` — Session identifier
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Messages
<details><summary><code>client.Messages.ListMessages(AgentSlug, OwnerID, SessionID) -> *funcateservergosdk.ListMessagesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List messages within a session for an owner with optional pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.ListMessagesRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
    SessionID: "<SESSION_ID>",
    Sort: funcateservergosdk.String(
        "-created_at",
    ),
    Filter: funcateservergosdk.String(
        "(author='user' && created_at>1732924800000)",
    ),
    Fields: funcateservergosdk.String(
        "id,author,created_at",
    ),
}
client.Messages.ListMessages(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>

<dl>
<dd>

**sessionID:** `string` — Session identifier
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — The page (aka. offset) of the paginated list (default to 1).
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `*int` — The max returned files per page (default to 30).
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Specify the ORDER BY fields. Add - / + (default) in front of the attribute for DESC / ASC order, e.g.: // DESC by created ?sort=-created_at
    
</dd>
</dl>

<dl>
<dd>

**filter:** `*string` 

Filter expression to filter/search the returned messages list, e.g.: ?filter=(author='user' && created_at>1732924800000)
The syntax basically follows the format OPERAND OPERATOR OPERAND, where: OPERAND - could be any field literal, string (single or double quoted), number, null, true, false OPERATOR - is one of: = Equal != NOT equal > Greater than >= Greater than or equal < Less than <= Less than or equal ~ Contains (for strings) !~ NOT contains (for strings) To group and combine several expressions you can use parenthesis (...), && (AND) and || (OR) tokens. Single line comments are also supported: // Example comment.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=id,author,created_at
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Messages.CreateMessage(AgentSlug, OwnerID, SessionID, request) -> *funcateservergosdk.CreateMessageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new message within a session for an owner
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.CreateMessageRequest{
    AgentSlug: "<AGENT_SLUG>",
    OwnerID: "<OWNER_ID>",
    SessionID: "<SESSION_ID>",
    Author: funcateservergosdk.CreateMessageRequestAuthorUser,
    Parts: []*funcateservergosdk.MessagePart{
        &funcateservergosdk.MessagePart{
            Type: funcateservergosdk.MessagePartTypeText,
            Text: funcateservergosdk.String(
                "Hello, how can I help you?",
            ),
        },
    },
    Stream: funcateservergosdk.Bool(
        false,
    ),
}
client.Messages.CreateMessage(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentSlug:** `string` — Agent slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — Owner identifier
    
</dd>
</dl>

<dl>
<dd>

**sessionID:** `string` — Session identifier
    
</dd>
</dl>

<dl>
<dd>

**author:** `*funcateservergosdk.CreateMessageRequestAuthor` — Message author
    
</dd>
</dl>

<dl>
<dd>

**parts:** `[]*funcateservergosdk.MessagePart` — Message parts
    
</dd>
</dl>

<dl>
<dd>

**stream:** `*bool` — Whether to stream the response as Server-Sent Events (SSE)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Authentication
<details><summary><code>client.Authentication.GetAuthMethods(AuthSlug) -> *funcateservergosdk.AuthMethodsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the supported authentication methods
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetAuthMethodsRequest{
    AuthSlug: "<AUTH_SLUG>",
}
client.Authentication.GetAuthMethods(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Authentication.AuthWithPassword(AuthSlug, request) -> *funcateservergosdk.AuthWithPasswordResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Login with username and password
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.AuthWithPasswordRequest{
    AuthSlug: "<AUTH_SLUG>",
    Username: "johndoe",
    Password: "secret_password",
}
client.Authentication.AuthWithPassword(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**username:** `string` — User's username
    
</dd>
</dl>

<dl>
<dd>

**password:** `string` — User's password
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Authentication.AuthRefresh(AuthSlug) -> *funcateservergosdk.AuthRefreshResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh JWT token using existing JWT token
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.AuthRefreshRequest{
    AuthSlug: "<AUTH_SLUG>",
}
client.Authentication.AuthRefresh(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Authentication.GetPublicToken(AuthSlug) -> *funcateservergosdk.AuthPublicResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get a public token for accessing public endpoints
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetPublicTokenRequest{
    AuthSlug: "<AUTH_SLUG>",
}
client.Authentication.GetPublicToken(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Users
<details><summary><code>client.Users.CreateUser(AuthSlug, request) -> *funcateservergosdk.CreateUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new user account with username and password
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.CreateUserRequest{
    AuthSlug: "<AUTH_SLUG>",
    Username: "johndoe",
    Password: "secret_password",
    PasswordConfirm: "secret_password",
}
client.Users.CreateUser(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>

<dl>
<dd>

**username:** `string` — User's username
    
</dd>
</dl>

<dl>
<dd>

**password:** `string` — User's password
    
</dd>
</dl>

<dl>
<dd>

**passwordConfirm:** `string` — Password confirmation
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Users.GetCurrentUser(AuthSlug) -> *funcateservergosdk.GetCurrentUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve the currently logged in user's profile
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetCurrentUserRequest{
    AuthSlug: "<AUTH_SLUG>",
}
client.Users.GetCurrentUser(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**authSlug:** `string` — Auth slug defined in funcate.yaml
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Files
<details><summary><code>client.Files.ListFiles(BucketSlug) -> *funcateservergosdk.ListFilesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of files from a bucket, supporting sorting and filtering. Note: Depending on the bucket's listRule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.ListFilesRequest{
    BucketSlug: "<BUCKET_SLUG>",
    Sort: funcateservergosdk.String(
        "-created,name",
    ),
    Filter: funcateservergosdk.String(
        "(name~'report' && size>1024)",
    ),
    Fields: funcateservergosdk.String(
        "id,name,size_bytes",
    ),
}
client.Files.ListFiles(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — The page (aka. offset) of the paginated list (default to 1).
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `*int` — The max returned files per page (default to 30).
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Specify the ORDER BY fields. Add - / + (default) in front of the attribute for DESC / ASC order, e.g.: // DESC by created and ASC by name ?sort=-created,name
    
</dd>
</dl>

<dl>
<dd>

**filter:** `*string` 

Filter expression to filter/search the returned files list, e.g.: ?filter=(name~'report' && size>1024)
The syntax basically follows the format OPERAND OPERATOR OPERAND, where: OPERAND - could be any field literal, string (single or double quoted), number, null, true, false OPERATOR - is one of: = Equal != NOT equal > Greater than >= Greater than or equal < Less than <= Less than or equal ~ Contains (for strings) !~ NOT contains (for strings) To group and combine several expressions you can use parenthesis (...), && (AND) and || (OR) tokens. Single line comments are also supported: // Example comment.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=id,name,size_bytes
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.UploadFile(BucketSlug, request) -> *funcateservergosdk.UploadFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upload a file to a bucket. Note: Depending on the bucket's createRule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.UploadFileRequest{
    BucketSlug: "<BUCKET_SLUG>",
    Content: strings.NewReader(
        "",
    ),
    ID: "id",
    ContentType: "contentType",
}
client.Files.UploadFile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.GetFile(BucketSlug, FileID) -> *funcateservergosdk.GetFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get metadata of a file. Note: Depending on the bucket's viewRule and access mode, the access to this action may or may not have been restricted. File ID, max length 36, first char must be alphanumeric, allowed chars: a-z A-Z 0-9 . - _ . 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetFileRequest{
    BucketSlug: "<BUCKET_SLUG>",
    FileID: "<FILE_ID>",
}
client.Files.GetFile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>

<dl>
<dd>

**fileID:** `string` — File ID, max length 36, first char must be alphanumeric, allowed chars: a-z A-Z 0-9 . - _ 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.DeleteFile(BucketSlug, FileID) -> *funcateservergosdk.DeleteFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a file from a bucket. Note: Depending on the bucket's deleteRule, the access to this action may or may not have been restricted. File ID, max length 36, first char must be alphanumeric, allowed chars: a-z A-Z 0-9 . - _ 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.DeleteFileRequest{
    BucketSlug: "<BUCKET_SLUG>",
    FileID: "<FILE_ID>",
}
client.Files.DeleteFile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>

<dl>
<dd>

**fileID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.ViewFile(BucketSlug, FileID) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

View file content directly in browser (inline). Note: Depending on the bucket's viewRule and access mode, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.ViewFileRequest{
    BucketSlug: "bucketSlug",
    FileID: "fileId",
}
client.Files.ViewFile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>

<dl>
<dd>

**fileID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.DownloadFile(BucketSlug, FileID) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Download file content as attachment. Note: Depending on the bucket's viewRule and access mode, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.DownloadFileRequest{
    BucketSlug: "bucketSlug",
    FileID: "fileId",
}
client.Files.DownloadFile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bucketSlug:** `string` — Slug of the bucket
    
</dd>
</dl>

<dl>
<dd>

**fileID:** `string` — File ID, max length 36, first char must be alphanumeric, allowed chars: a-z A-Z 0-9 . - _ 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Records
<details><summary><code>client.Records.ListRecords(LitedbSlug, TableID) -> *funcateservergosdk.ListRecordsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated records list from a table or view, supporting sorting, filtering, and other query operations. Note: Depending on the table's listRule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.ListRecordsRequest{
    LitedbSlug: "<LITEDB_SLUG>",
    TableID: "<TABLE_ID>",
    Sort: funcateservergosdk.String(
        "-created,id",
    ),
    Filter: funcateservergosdk.String(
        "(title~'abc' && created>'2022-01-01')",
    ),
    Fields: funcateservergosdk.String(
        "*",
    ),
}
client.Records.ListRecords(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**litedbSlug:** `string` — Slug of the LiteDB service
    
</dd>
</dl>

<dl>
<dd>

**tableID:** `string` — Name of the table or view. For views, only list and get operations are supported.
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — The page (aka. offset) of the paginated list (default to 1).
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `*int` — The max returned records per page (default to 30).
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Specify the ORDER BY fields. Add - / + (default) in front of the attribute for DESC / ASC order, e.g.: // DESC by created and ASC by id ?sort=-created,id
    
</dd>
</dl>

<dl>
<dd>

**filter:** `*string` 

Filter expression to filter/search the returned records list, e.g.: ?filter=(title~'abc' && created>'2022-01-01')
The syntax basically follows the format OPERAND OPERATOR OPERAND, where: OPERAND - could be any field literal, string (single or double quoted), number, null, true, false OPERATOR - is one of: = Equal != NOT equal > Greater than >= Greater than or equal < Less than <= Less than or equal To group and combine several expressions you can use parenthesis (...), && (AND) and || (OR) tokens. Single line comments are also supported: // Example comment. 
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=*
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Records.CreateRecord(LitedbSlug, TableID, request) -> *funcateservergosdk.GetRecordResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new record in the specified table. Note: This operation is only supported for tables, not for views. Depending on the table's create rule, the access to this action may or may not have been restricted. When primary key is not auto increment, then must specify the primary key `id` value in the request body. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.CreateRecordBody{
    LitedbSlug: "<LITEDB_SLUG>",
    TableID: "<TABLE_ID>",
    Fields: funcateservergosdk.String(
        "*",
    ),
    Body: map[string]any{
        "active": true,
        "id": "97cc3d3d-3804-4669-97b9-567572fb6653",
        "title": "Example record",
    },
}
client.Records.CreateRecord(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**litedbSlug:** `string` — Slug of the LiteDB service
    
</dd>
</dl>

<dl>
<dd>

**tableID:** `string` — Name of the table (views are not supported for create operations).
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=*
    
</dd>
</dl>

<dl>
<dd>

**request:** `funcateservergosdk.CreateRecordRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Records.GetRecord(LitedbSlug, TableID, RecordID) -> *funcateservergosdk.GetRecordResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single record by its ID. Note: When using a view name (tableOrViewName), only list and get operations are supported. Depending on the table's view rule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.GetRecordRequest{
    LitedbSlug: "<LITEDB_SLUG>",
    TableID: "<TABLE_ID>",
    RecordID: "<RECORD_ID>",
    Fields: funcateservergosdk.String(
        "*",
    ),
}
client.Records.GetRecord(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**litedbSlug:** `string` — Slug of the LiteDB service
    
</dd>
</dl>

<dl>
<dd>

**tableID:** `string` — Name of the table or view. For views, only list and get operations are supported.
    
</dd>
</dl>

<dl>
<dd>

**recordID:** `string` — ID of the record to retrieve.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.:?fields=*
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Records.DeleteRecord(LitedbSlug, TableID, RecordID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a single record by its ID. Note: This operation is only supported for tables, not for views. Depending on the table's delete rule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.DeleteRecordRequest{
    LitedbSlug: "<LITEDB_SLUG>",
    TableID: "<TABLE_ID>",
    RecordID: "<RECORD_ID>",
}
client.Records.DeleteRecord(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**litedbSlug:** `string` — Slug of the LiteDB service
    
</dd>
</dl>

<dl>
<dd>

**tableID:** `string` — Name of the table (views are not supported for delete operations).
    
</dd>
</dl>

<dl>
<dd>

**recordID:** `string` — ID of the record to delete.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Records.UpdateRecord(LitedbSlug, TableID, RecordID, request) -> *funcateservergosdk.GetRecordResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates a single record by its ID. Note: This operation is only supported for tables, not for views. Depending on the table's update rule, the access to this action may or may not have been restricted. 
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &funcateservergosdk.UpdateRecordBody{
    LitedbSlug: "<LITEDB_SLUG>",
    TableID: "<TABLE_ID>",
    RecordID: "<RECORD_ID>",
    Fields: funcateservergosdk.String(
        "*",
    ),
    Body: map[string]any{
        "active": false,
        "title": "Updated record",
    },
}
client.Records.UpdateRecord(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**litedbSlug:** `string` — Slug of the LiteDB service
    
</dd>
</dl>

<dl>
<dd>

**tableID:** `string` — Name of the table (views are not supported for update operations).
    
</dd>
</dl>

<dl>
<dd>

**recordID:** `string` — ID of the record to update.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `*string` — Comma separated string of the fields to return in the JSON response (by default returns all fields). Ex.: ?fields=*
    
</dd>
</dl>

<dl>
<dd>

**request:** `funcateservergosdk.UpdateRecordRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

