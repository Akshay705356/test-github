pipeline {
    agent any
    stage('master-branch-stuff') {
    when {
        branch 'master'
    }
    steps {
        echo 'run this stage - ony if the branch = master branch'
      }
    }
   stage('feature-branch-stuff') {
    when {
        branch 'feature/*'
    }
    steps {
        echo 'run this stage - only if the branch name started with feature/'
    }
} 
    stage('expression-branch') {
    when {
        expression {
            return env.BRANCH_NAME != 'master';
        }
    }
    steps {
        echo 'run this stage - when branch is not equal to master'
    }
}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
