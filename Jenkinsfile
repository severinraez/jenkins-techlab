properties([
    buildDiscarder(logRotator(numToKeepStr: '5')),
    pipelineTriggers([
        pollSCM('H/5 * * * *'),
        cron('@midnight')
    ]),
    parameters([string(defaultValue: 'bar', description: '', name: 'foo')])
])


properties([, pipelineTriggers([])])

timestamps() {
    timeout(time: 10, unit: 'MINUTES') {
        node {
            stage('Greeting') {
                echo "Value of foo is ${env.foo}"
            }
        }
    }
}