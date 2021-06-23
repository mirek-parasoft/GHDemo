pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Building stage' 
                sh 'mkdir -p build && cd build && cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON .. && make'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing stage' 
                sh 'cd build && /home/demo-user/Parasoft/cpptest/cpptestcli -compiler gcc_10-64 -config "builtin://MISRA C 2012" -input compile_commands.json'
                recordIssues tool: parasoftFindings(pattern: "reports/report.xml")
            }
        }
        stage('Archive stage') {
            steps {
                echo 'Hello world!'
            }
        }
    }
}