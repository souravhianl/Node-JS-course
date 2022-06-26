var fs = require('fs');

/*
The fs. unlink() method is used to remove a file or symbolic link from the filesystem.
This function does not work on directories, therefore it is recommended to use fs.
*/

//fs.mkdirSync('stuff');

//fs.rmdirSync('stuff');

fs.mkdir('stuff', function(){
    fs.readFile('readMe.txt', 'utf8', function(err, data){

        if (err) console.log(err);

        fs.writeFile('./stuff/writeMe.txt',data, (err) => {

            if (err) console.log(err);
        });
    });
});

// when directory is not empty
fs.unlink('./stuff/writeMe.txt', function(){
    fs.rmdirSync('stuff');
})