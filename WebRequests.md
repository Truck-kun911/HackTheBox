# cURL
| Command | Description |
| --- | --- |
| curl -h | cURL help menu |
| curl https://example.com | fetches the HTML content of the website at any url |
| curl -s -O https://example.com/index.html | Download file |
| curl -k https://example.com | skips https (SSL) certificate vadilation |
| curl -v https://example.com | Shows detailed information about the request and response, including headers and data exchange |
| curl -I https://example.com | Send HEAD request (only prints response headers) |
| curl -i https://example.com | Print response headers and response body |
| curl https://example.com -A 'Mozilla/5.0' | set user-agent header |
| curl -u user:password https://<SERVER_IP>:<PORT>/ | Set HTTP basic authorization credentials |
| curl http://user:password@<SERVER_IP>:<PORT>/ | Pass HTTP basic authorization credentials in the URL |
| curl -H 'Authorization: Basic YWRtaW46YWRtaW4=' http://<SERVER_IP>:<PORT>/ | Set request header |
| curl 'http://<SERVER_IP>:<PORT>/search.php?search=le' | Pass GET parameters |
| curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/ | Send POST request with POST data |
|  curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://<SERVER_IP>:<PORT>/ | set request cookies |
| curl -X POST -d '{"search":"london"}' -H 'Content-Type: application/json' http://<SERVER_IP>:<PORT>/search.php | Send POST request with JSON data |

# API
| Command | Description |
| --- | --- |
|  curl http://<SERVER_IP>:<PORT>/api.php/city/london | read entry |
|  curl -s http://<SERVER_IP>:<PORT>/api.php/city/ (pipe key) jq | read all entries |
| curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json' | create entry |
| curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json' | update entry |
|  curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | delete entry |

# Browser DevTools
| Shortcut | Description |
| --- | --- |
|  [CTRL+SHIFT+I] or [F12] | show devtools|
|  [CTRL+SHIFT+E] | show network tab |
|  [CTRL+SHIFT+K] | show console tab |
