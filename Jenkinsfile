node ('DOTNETCORE') {
    stage('SCM') {
	echo 'Gathering code from version control'
    git branch: "${branch}", url: "https://github.com/ahmed-gharib89/automating-jenkins-groovy"
    }
    stage('Build') {
        echo 'Building....'
        sh '''
            dotnet --version
            dotnet build ConsoleApp1
        '''
        echo 'release notes ...'
        releasenotes()
    }
    stage('Test') {
        echo 'Testing....'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
    stage ('Completed') {
        echo 'Completed ...'
    }
}