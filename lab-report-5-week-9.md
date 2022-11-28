**Lab Report 5**

---

grade.sh code block = 


```
set -e



rm -rf student-submission
git clone $1 student-submission

FILE=student-submission/ListExamples.java
if [ -f "$FILE" ]; then
    echo "file exists."
    echo "pass"
else 
    echo "$File does not exist"
    echo "fail"
fi


cp student-submission/ListExamples.java LIST-EXAMPLES-GRADER


javac -classpath/LIST-EXAMPLES-GRADER/ListExamples.java; [ $? -eq 0 ] && echo "ok" || echo "compilation error!"

```


running it with varius repositories : 



1. ![Image](https://user-images.githubusercontent.com/114611146/204357800-fd400b34-a280-46bf-987e-9fed3611eabe.png)

Trace : 

Line 1 : sets -e

Line 2 : removes the original student submission

Line 3 : clones this repository as the new student submission 

Line 4 : Names the ListExamples.java file in the student submission as FILE

Line 5 : if the FILE exists in repository(true)

Line 6 : echo "file exists" ---> TRUE

Line 7 : echo "tests passed' (exit code is 0)

Line 8 : if it does not exist

Line 9 : echo "file does not exist" (exit code is 1)



2. ![Image](https://user-images.githubusercontent.com/114611146/204357804-68c5e445-9a3e-473e-a295-fa08b8d041f4.png)


3. ![Image](https://user-images.githubusercontent.com/114611146/204357807-36893de0-efb4-44cd-ac23-12c941076635.png)

