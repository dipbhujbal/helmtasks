## Task4 
**Note: Use the sample helm chart created earlier 
1. Creat a configmap with name <HELM_RELEASE_NAME>-nginx-configmap and mount it as a volume in the deployment

 configmap.yaml snippet :
  ```
  kind: ConfigMap
  metadata:
    name: {{ .Release.Name }}-nginx-configmap
  ```
  
  
  deployment.yaml snippet: 
  
  ```
            volumeMounts:
          - name: mnt
            mountPath: /usr/share/nginx/html/index.html
            subPath: index.html
      volumes:
         - name: mnt
           configMap:
            name: {{ .Release.Name }}-nginx-configmap
  
  ```
