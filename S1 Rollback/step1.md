In this scenario, we are going to teach our users how to make use of the autocommit, Commit, and Rollback functions introduced in InnoDB

Typically individual DML (Insert, Update, Delete) statements are performed in an autocommit transaction, 
which those commands are committed as soon as the statement successfully completes. 
There will be no opportunity to roll back the database to the state prior to the statement if autocommit is enabled. 
When something goes wrong, the only restoration option available is to reconstruct the data from a backup (providing one exists).

In MySQL, autocommit is on by default for InnoDB, here in this case, we are going to teach you how to disable this option.

First, we want to setup a enviroment first:
Pulliing the MySQL image and running it on a docker container

 `docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=root mysql:latest`{{execute}} 

Run the MySQL container in Interactive Mode to get access of the bash shell of the container
 `docker exec -it mysql bash`{{execute}} 

Now we can login into our mySQL database with user ROOT
 `mysql -u root -proot`{{execute}} 


<pre>
[ -d /home/scrapbook/tutorial/.git ] && echo "done"
</pre>

If you run `git init`{{execute}}, you will be allowed to continue.

The `index.json` example is:
<pre>
"details": {
    "steps": [
        {
            "title": "Step 1 - Verify",
            "text": "step1.md",
            "verify": "step1-verify.sh"
        }
    ]
}
</pre>
