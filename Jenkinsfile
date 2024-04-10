pipeline{
    agent {
        label 'nop'
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('scm') {
           steps {
                git url: 'https://github.com/venky1520/nopCommerce-apr24.git',
                    branch: 'develop'
           } 
        }
        stage('build') {
            steps {
                sh 'dotnet publish -o published/ -c Release src/Presentation/Nop.Web/Nop.Web.csproj'
            }
        }
    }
}
