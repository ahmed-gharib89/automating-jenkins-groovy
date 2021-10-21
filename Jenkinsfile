node ('master') {
    stage('SCM') {
	echo 'Gathering code from version control'
    git branch: "${branch}", url: "https://github.com/ahmed-gharib89/automating-jenkins-groovy"
    }
    stage('Build') {
        echo 'Building....'
        if (env.NODE_NAME == 'DOTNETCORE') {
            sh '''
                dotnet --version
                dotnet build ConsoleApp1
            '''
        } else {
            echo "Skipping build on ${env.NODE_NAME}"
        }
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
    stage ('Success') {
        echo 'Success ...'
        sh 'ls -lah'
        // Archive the build artifacts and releasenotes.txt
        archiveArtifacts artifacts: '*releasenotes.txt', followSymlinks: false
    }
}