pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'python --version'
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/**/*.py*')
            }
        }
    }
}