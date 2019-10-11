# Advance Bash notes :taco:

## Linux is extensionless
  .txt means nothing --> except for us humans

## Everything is a file
. is a file
text.txt is a file
directory_folder/ is a file

## Linux Permission

Things a user can do:
Read(r)
Write(w)
Execute(x)

Users that exist:
- owner / user
Typically the person/user who create the file. however, it can be changed.
- group
Every File belong a a single group. Groups have many users in it and give access to multiple people
- others
Everyone else not in a group or the owner.

#### Changing Permissions:

chmod <permissions> <path/file>

![binary of chmod](https://danielmiessler.com/images/permissions.png)

## Streams, Redirects and Piping

### Streams
- STDIN
  - Standard input
  - STDIN code is 0
- STDOUT
  - Standard output
  - STDOUT code is 1
- STDERR
  - Standard Error
  - STDERR code is 2


### Piping and Redirects
Means we can join all these amazing command together :)

### Redirecting
#### This is redirecting of STDOUT
 ls > list_of_ls.tx

 wc words.txt > word_count.txt

 cat words.txt >> word_count.txt

#### This is redirecting of STDIN

wc < words.tx


#### Redirecting STDERR

ls non_file_existing 2> log.txt


### Piping |
We sent STDOUT and STDERR into files, but what we want is to be able to send outputs into other programs. This is very powerful :fire: and is called Piping :taco:

sort words.txt | head -4

ls | head -3

ls | tail -3

cat example.txt | grep When


### Process Management

  top

  ps

  ps aux

  ps aux | grep aux > ps_aux_logs.txt

  ps aux | grep vagrant > ps_vagrant_logs.txt

  ps aux | grep vagrant nwejf 231  2>> ps_vagrant_logerror.txt

##### To kill use kill and the process ID (pid)

  kill <pid>

##### Sending process to background

###### Process in foreground
  sleep 100

###### Process in the background

  sleep 100 &

  ps aux | grep sleep

  kill 2472
