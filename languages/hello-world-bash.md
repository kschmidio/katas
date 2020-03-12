# Hello World bash


## Prerequisites
* Your favorite Linux environment

## Steps
1. create a file `touch kata.sh`
2. optional : open it with Vim and change the colors first `:set background=dark`
3. write a simple script
   ```
   #!/bin/bash

   echo "Hello Kata"
   echo "number of arguments " $#
   echo "all arguments " $*

   printDate() {
     date=$(date)
     echo "Today's date is $date"
   }

   countFiles() {
     files=$(ls | wc -l)
     if [ $files -eq 1 ]
     then
       echo "You only have one file"
     else
       echo "You have $files files"
     fi
   }

   countLinesWordsCharacters() {
     for result in $(ls)
       do
         echo $(wc $result)
     done
   }

   main() {
     dateResult=$(printDate)
     echo $dateResult
     echo $?
     countFiles
     countLinesWordsCharacters
   }

   main
   ```
4. make it executable and run it