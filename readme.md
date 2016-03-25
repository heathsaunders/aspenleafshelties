# Project Name

## Installation
# Get this up and running with the following docker commands

switch to the src directory

#create the website image which includes src files
docker build -t aspenwww -f /src/Dockerfile .

#this uses a standard docker mysql image sets up the database and runs the two sql files to build. In the future this database must be persistant somehow.
docker run --name aspenmysql -d -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=kdavidso_aspenleaf -v /c/Users/jjenkins/Documents/projects/aspenleaf/aspenleafshelties/sql/runonce:/docker
-entrypoint-initdb.d mysql

docker run -d --name www --link aspenmysql:mysql aspenwww

TODO: Describe the installation process

## Usage

TODO: Write usage instructions

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

TODO: Write history

## Credits

TODO: Write credits

## License

TODO: Write license