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
        sh 'ls -lah'
        sh 'pwd'
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
    post {
        success {
            echo 'Success ...'
            // Archive the build artifacts and releasenotes.txt
            archiveArtifacts artifacts: 'releasenotes.txt', followSymlinks: false
        }
    }
}