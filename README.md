Caso práctico N° 3 - Teleinformática

> [!NOTE]
> Como correr el caso
1. Clonar el repo
2. Ingresar a la carpeta case3:
```
cd case3
```
3. Aplicamos las configuraciones de los recursos de la base de datos: 
```
kubectl apply -f db/
```
4. Aplicamos las configuraciones de los recursos de la app metabase:
```
kubectl apply -f metabase/
```
6. Debido al tamaño del dump, k8s dió errores 413 (Content to large). Por lo vamos a levantarlos de otra manera, corriendo:
```
cat mobility-postgre | kubectl exec -it pods/db-mobility-0 -- psql -h localhost -U postgres -d mobility
```
7. Ingresar a https://cchiappone-metabase.my.kube.um.edu.ar y abrir la consulta guardada para visualizar los datos:
![image](https://github.com/ml-cchiappone/tele2024/assets/58527941/ff7a141c-2e7d-473f-9180-028ffbf748ba)

