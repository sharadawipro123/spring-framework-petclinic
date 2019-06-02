node  { stage ('scm checkout')

    git credentialsId: 'sharadawipro123', url: 'https://github.com/sharadawipro123/spring-framework-petclinic.git'
       stage('java build'){
           sh 'mvn clean install'
       }

        stage ('sh Build'){
        sh '/usr/bin/docker build -t sharadagaikwad/target:v2 .'
            
        }
stage('push docker image'){
withCredentials([usernamePassword(credentialsId: 'sharadagaikwad', passwordVariable: 'Pushdocker', usernameVariable: 'sharadagaikwad')])
{
sh '/usr/bin/docker login -u $sharadagaikwad -p $Pushdocker'
}

    sh '/usr/bin/docker push sharadagaikwad/target:v2'

}   
}

