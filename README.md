# Git-Basic
Q1. How would you move your local repo to a remote GitHub repo?
Describe the step you would take to add the remote GitHub repo,Push your local changes and verify that the files were successfully transferred.
=> after git init command the (main) becomes (master).that means a .git file will be created
=> git -lsart for checking the local repo files.
=> cd ..
=> git pull "link of remote repo"///in which dir the local repo is present
=> cat file.txt //update anything.
=> git status //modified: file.txt in red
=> git add .//it will add the file in staging phase
=> git commit
=> cd .git/objects  ///it will open all git objects .whenever any object is created automatically and it used the starting(2) chars of the git file name chars.(40)chars ...and we can create the objects mannualy.
=> git push "remote repo link"  ///it will reflect error
=> git remote add origin "link'
=> git push origin head
practical 2:


prac 3:
git init
git hash-object -w filename
1e4ff029aee68d0d69ef9eb6efa6cbf1ec732f99
a39a620dae5bc8b4e771cd4d251b7d080401a21e
vi filename->100644 blob shacode->esc:wq
cat filename | git mktree
git read-tree <code>
Write the steps and then perform to move file from:
a.remote repo to local repo
b.from local to staging area(remove prac3)
c.from staging to working directory

git init
git fetch <url>(here it will move the files from remote repo to local repo)
cd .git/objects(to check the blob to the local repo)
cd<2 char of object>
ls
git cat-file -t <sha-1 code of blob>  #it will give the type of object
git cat-file -p <sha-1 code of blob>  #it will give the contents of the object
vi filename
100644 blob <code> tab file.txt
cat filename(note:which is created above with vi editor take that file name) | git mktree
git read-tree <sha-1code of above created> #it will add the file in the staging area
git ls-files -s #to check the files in staging area
git status
ls
git checkout-index -a#it will move the file from staging area to working directory


-----------------------------------------practical 5---------------------------------------
(1.git add #by default bolb created
 2.git hash-object filename #manualy blob created
 3.
 4.echo "first blob is created" | git hash-object -w --stdin #blob will be created without any file name in local repo..but not visible in ls.
 
)
1.create the 2 blob with the name: arindam.txt maji.txt but create it without working directory.

=>echo "first blob is created" | git hash-object -w --stdin(ab951342bee3a2ce99d7dfc8f2b6227c386c1f20)
=>echo "second blob is created" | git hash-object -w --stdin(40b47f9ac57c03b5f8a75c5fbb8a963b0e47edc1)
=>vi f1.txt
=>100644 bolb <code> tab arindam.txt
=>100644 bolb <code> tab maji.txt
=>cat f1.txt(note:which is created above with vi editor take that file name) | git mktree (eb7689f5d69fa74f2f769c9e2da117d802b34fde)

2.move this blobs to the staging area and then to the working directory

=>git read-tree <sha-1code of above created> #it will add the file in the staging area
=>git ls-files -s #to check the files in staging area
=>ls
=>git checkout-index -a#it will move the file from staging area to working directory
=>ls

3.create one snapshot for this.

=>git commit -m"first commit"
ss

4.modify the contents of first blob and then create the second snapshot.

=>cat>>arindam.txt
=>bla..blaa...bla....
=>git commit -m"second commit"#it will through a error because vi needs to move the file to the staging area
ss

5.compare the contents of modify file.

=>git diff

6.compare the contents of 2 snapshots.
=>
7.find all the alphabets in local repo and find the
