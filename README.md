# Kubectl with docker
This image is for usage in docker pipeline.

Exemple:

```groovy
withCredentials([[$class: 'FileBinding', credentialsId: 'kubeconfig', variable: 'KUBEFILE']]) {
    docker.image('prodomaines/kubectl:v-1.3.5').inside {
        sh "kubectl --kubeconfig=$env.KUBEFILE version"
    }
}
```
