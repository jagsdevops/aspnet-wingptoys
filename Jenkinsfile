pipeline{
	agent { label 'msbuild' }
	stages{
		stage('Code-Check'){
			steps{
				echo "Example stage"
			}
		}
    		stage('Build'){
			steps{
				bat " \"${tool 'msbuild15'}\" build.xml /p:Configuration=Debug"
			}
		}
	}
	post{
		always{
            echo "todo: archiveArtifacts"
		}
		failure{
			echo "yikes, build broke"
		}
	}
}
