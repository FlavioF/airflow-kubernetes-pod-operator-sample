# About this repo

A simple sample on how to use Google Composer and Kubernetes Pod Operator

## airflow-kubernetes-pod-operator
A simple sample on how to use Airflow with KubernetesPodOperator base on [Airflow on Kubernetes (Part 1): A Different Kind of Operator](https://kubernetes.io/blog/2018/06/28/airflow-on-kubernetes-part-1-a-different-kind-of-operator/)

**Usefull links:**
- [Samples](https://github.com/GoogleCloudPlatform/python-docs-samples/blob/master/composer/workflows/kubernetes_pod_operator.py)
- [Source Code](https://github.com/apache/incubator-airflow/blob/v1-10-stable/airflow/contrib/operators/kubernetes_pod_operator.py)
- [Pod Operator in Cloud Composer](https://cloud.google.com/composer/docs/how-to/using/using-kubernetes-pod-operator)
- [Airflow Operator](https://github.com/GoogleCloudPlatform/airflow-operator)

# How to use this sample

- Prepare deploy
```
mkdir sample
find -name '*.py' -o -name '*.sql' | xargs cp -t sample/
```

- Download and prepare requirements (if need)
```
mkdir pkg
pip install --install-option="--install-lib=$PWD/pkg" -r requirements.txt
mv pkg/ sample/pkg
```

- Deploy dag
```
gcloud composer environments storage dags import \
                            --project <project> \
                            --environment <cluster> \
                            --location <location> \
                            --source sample
```

- Check your Airflow Web UI :)