properties([
    buildDiscarder(logRotator(numToKeepStr: '5')),
    pipelineTriggers([
        pollSCM('H/5 * * * *'),
        cron('@midnight')
    ]),
    parameters([string(defaultValue: 'bar', description: '', name: 'foo')])
])

timestamps() {
    timeout(time: 10, unit: 'MINUTES') {
        node {
            stage('Greeting') {
                echo "Value of env foo is ${env.foo}, value of foo is ${foo}"
            }
        }
    }
}