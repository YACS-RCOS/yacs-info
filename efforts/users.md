# Users Login/Events


**Things to Change:**

Schema Changes:

createdAt, all dates -> psql:date
all schema to snake_case
uid -> user_id

add header field as json, and content -> json

---

auth:

free text username
- unique
- no white space
- alphanum (UTF8)

abs free password:
- *
- hash and salt (sha256)

---

cut off the "s"

---

event:


All users are fingerprinted first time they enter the site.
$(uuid) -> localstorage & cookie

A user that has not logged in:

event {
  fingerprint: uuid,
  user_name: None
}

if someone goes to different computer:

if they login (user_name)
^
event {
  headers/profile: ... (web browser, ip,...)
  fingerprint: uuid_0,
  user_name: a,
  data: _json_ free
}

event {
  headers/profile: ... (web browser, ip,...), _json_
  fingerprint: uuid_1,
  user_name: a,
  data: _json_ free
}

_Example query to find browser from user_
`select header -> web_browser from event where user_name = ...`
