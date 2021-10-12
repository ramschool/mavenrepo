pipeline{
agent { label 'slave' }
stages{

stage('Gitstage'){
steps{
checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'b6e2c3d8-08e1-44c7-beac-904ab9a8f07f', url: 'https://github.com/ramschool/mavenrepo.git']]])
 
		}		
 	 } //stage1 close

stage('Buildstage'){
steps{
sh 'mvn package'
	}
        } //stage2 close



stage('Deploy'){
steps{
sh 'mvn deploy'	
	}
	} //stage4 close

stage('SCP'){
steps{
sh 'scp /root/workspace/SampleProject/target/studentapp-2.5-SNAPSHOT.war 13.126.117.127://var/lib/tomcat/webapps'
	}
	} //stage5 close

       } // stages close

	} // pipiline close
