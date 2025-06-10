pipeline{
agent any

tools{
maven 'Maven'
}

stages{
stage('Checkout'){
steps{
git branch: 'master', url:'https://github.com/milli1331/mymvnapp.git'
}
}

stage('Build'){
steps{
sh 'mvn clean package'
}
}

stage('Test'){
steps{
sh 'mvn test'
}
}

stage('Run Application'){
steps{
sh 'java -jar target/mymvnapp-1.0-SNAPSHOT.jar'
}
}

post{
success{
echo 'maven build and deployed'
}

failure{
echo 'failed'
}
}
}
