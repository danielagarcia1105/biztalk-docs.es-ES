---
title: Usar el adaptador de base de datos de Oracle con SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa6e5f92bcb1ddd579b70912b98fc0f08165bca6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975381"
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a>Usar el adaptador de base de datos de Oracle con SharePoint
El Asistente de desarrollo del servicio de adaptador de WCF para [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] habilita el adaptador de Microsoft BizTalk para que Oracle Database y Microsoft BizTalk Adapter para Oracle E-Business Suite debe usarse directamente como un origen de datos externo de Microsoft SharePoint. Se inicia el Asistente para agregar un desarrollo de servicio que admita esta característica con el **servicio de adaptador de WCF** plantilla para crear un nuevo Visual C# sitios Web en [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]. La plantilla se incluye con el [!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]. También debe instalar el SDK de adaptador de línea de negocio (LOB) de Microsoft Windows Communication Foundation (WCF).  
  
## <a name="sharepoint-operation-support"></a>Compatibilidad con la operación de SharePoint  
 El Asistente de desarrollo de servicios de adaptador genera un contrato de servicio especial para los adaptadores de Oracle que es compatible con Microsoft SharePoint. El asistente generará un contrato de servicio que incluye las siguientes operaciones para el adaptador de la integración con SharePoint de Microsoft:  
  
- **Crear:** compatibles con la operación CreateItem_.  
  
- **Lectura:** compatibles con la operación ReadItem_.  
  
- **Actualización:** compatible con la operación UpdateItem_.  
  
- **Delete:** compatibles con la operación DeleteItem_.  
  
- **Consulta:** compatibles con la operación ReadList.  
  
- **Asociar:** compatibles con la operación Associate_.  
  
  El siguiente contrato de servicio se generó utilizando para el adaptador de Microsoft BizTalk para Oracle Database como ejemplo. El adaptador está configurado para proporcionar acceso a la tabla EMP  
  
```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface ISCOTT_EMP {  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadList(System.Nullable<int> Limit);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void CreateItem(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void UpdateItem_EMPNO(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void DeleteItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] Associate_DEPTNO(System.Nullable<decimal> DEPTNO);  
}  
```  
  
## <a name="create-a-new-web-site-to-host-the-oracle-database-in-iis"></a>Crear un nuevo sitio Web para hospedar la base de datos de Oracle en IIS  
 Estos pasos proporcionan un ejemplo con el Asistente de desarrollo de servicio del adaptador de WCF, para crear un nuevo servicio web WCF aloja el adaptador de Microsoft BizTalk para Oracle Database. El contrato de servicios incluye operaciones directamente compatibles con Sharepoint. Por lo que puede consumir directamente como un origen de datos externo. El adaptador está configurado para autenticarse con la base de datos de Oracle mediante el **SCOTT** cuenta. Si el **SCOTT** cuenta está bloqueada, puede desbloquear la cuenta iniciando sesión en SQL Plus como SYSDBA.  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 A continuación, ejecute el siguiente comando.  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a>Crear el nuevo proyecto de sitio Web  
  
1. Abra Visual Studio.   
  
2. En Visual Studio, en el **archivo** menú, seleccione **New** y, a continuación, haga clic en **proyecto**.  
  
3. En el **nuevo proyecto** cuadro de diálogo, expanda **otros lenguajes** y haga clic en **Visual C#**. Buscar el **servicio de adaptador de WCF** en la plantilla de lista y haga clic en él para seleccionarlo.  
  
   > [!NOTE]
   >  El **servicio de adaptador de WCF** plantilla no está disponible si el [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)] no está instalado. En x64 de sistemas, se instalan las versiones x86 y x64 de la [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)].  
  
4. Especificar **ScottEMP** para el nombre y, a continuación, haga clic en **Aceptar**. El **Asistente para desarrollo del servicio de adaptador de WCF** se inicia.  
  
5. En el **Introducción** página, haga clic en **siguiente**.  
  
6. En el **elija operaciones** , especifique el **oracleDBBinding** enlace.  
  
7. Haga clic en el **configurar** botón. El **configurar el adaptador** muestra el cuadro de diálogo.  
  
8. En el **seguridad** ficha, seleccione **Username** en el **tipo de credencial de cliente** cuadro de lista desplegable.  
  
9. Escriba **SCOTT** para el usuario el nombre y escriba la contraseña correcta para la cuenta de SCOTT. La contraseña predeterminada para la cuenta de SCOTT es **tiger**.  
  
10. Haga clic en el **propiedades de URI** , escriba el nombre de host o dirección IP del servidor de Oracle en el **ServerAddress** cuadro.  
  
11. Escriba el nombre de instancia correcto de servicio base de datos de Oracle en el **ServiceName** cuadro. Puede copiar la información de nombre de instancia de Oracle Enterprise Manager.  
  
12. Presione el **Aceptar** situado en la **configurar el adaptador** cuadro de diálogo  
  
13. En el **elija operaciones** página del asistente, haga clic en el **Connect** botón y espere unos minutos para las categorías que se van a compilar en la base de datos de Oracle.  
  
14. Una vez agregadas las categorías en el **seleccionar una categoría** lista, desplácese hacia abajo hasta **SCOTT** y expándalo. A continuación, expanda **tabla** y haga clic en el **EMP** entrada de la tabla.  
  
15. En el **operaciones y categorías disponibles** lista, seleccione todas las operaciones en la lista y haga clic en el **agregar** botón. Todas las operaciones se agregan a la **agregar categorías y operaciones** lista.  
  
16. En el **elija operaciones** página, haga clic en el **siguiente** botón.  
  
17. En el **configurar el servicio y los comportamientos de extremo** , establezca el **UseServiceCertificate** el comportamiento de servicio **false** en este ejemplo. A continuación, haga clic en el **siguiente** botón.  
  
18. En el **configurar el enlace de punto de conexión de servicio y dirección** página, haga clic en el **aplicar** botón. A continuación, haga clic en el **siguiente** botón.  
  
19. En el **resumen** página, haga clic en el **finalizar** botón.  
  
20. Haga clic en el **compilar** opción de menú y, a continuación, haga clic en **compilar solución**. Comprobar que la compilación del proyecto se realizó correctamente sin errores.  
  
## <a name="publish-the-new-service-to-iis"></a>Publicar el nuevo servicio en IIS  
 En este ejemplo publicará el servicio de adaptador de host para el servidor web IIS local.  
  
1.  Haga clic en el Explorador de soluciones para Visual Studio, el **ScottEmp** del proyecto y haga clic en **propiedades**. Se muestran las pestañas del Diseñador de proyectos.  
  
2.  Haga clic en el **Web** y, después, haga clic en el **servidor Web de IIS Local Use** opción.  
  
3.  Haga clic en el **crear directorio Virtual** botón.  
  
4.  Abra un explorador web a la dirección de servicio **http://localhost/ScottEmp/ISCOTT_EMP.svc**. Debería recibir un mensaje que indica "Se ha creado un servicio" que indica el adaptador se hospeda en IIS.  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a>Agregar el origen de datos externo en un sitio de SharePoint mediante SharePoint Designer  
 En esta sección se describe cómo agregar el servicio de WCF como origen de datos externo a un nuevo sitio Web mediante SharePoint Designer.  
  
  
1.  Abra SharePoint Designer y cree un nuevo sitio Web.  
  
2.  En SharePoint Designer, expanda **navegación** y haga clic en **tipos de contenido externo** en el **objetos del sitio** lista.  
  
3.  Haga clic en el **External Content Type** botón de menú para crear un nuevo tipo de contenido externo.  
  
4.  Haga clic en el texto al lado de **nombre** para editar el nombre del nuevo tipo de contenido externo. Escriba **OracleEMP** para el nombre.  
  
5.  Haga clic en el vínculo de texto junto a **sistema externo** que dice **haga clic aquí para detectar orígenes de datos externos y las operaciones.**. Se abre el Diseñador de la operación para el tipo de contenido externo OracleEMP.  
  
6.  Haga clic en el **Agregar conexión** botón en la pantalla de detección.  
  
7.  En el cuadro de diálogo de selección de tipo de origen de datos externo, elija **servicio WCF** y haga clic en el **Aceptar** botón.  
  
8.  En el cuadro de diálogo de conexión de WCF, en el **dirección URL de metadatos de servicio** escriba **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**  
  
9. En el **dirección URL del punto de conexión de servicio** escriba **https://localhost/ScottEmp/ISCOTT_EMP.svc**  
  
10. Haga clic en el **Aceptar** botón para cerrar el cuadro de diálogo de conexión de WCF.  
  
11. Una vez que se rellene la información de origen de datos, expanda el **https://localhost/ScottEmp/ISCOTT_EMP.svc** origen de datos y expanda **métodos Web**.  
  
12. Haga clic en el **ReadList** método Web y haga clic en **nueva operación de lista de lectura**. Se inicia el cuadro de diálogo de configuración de lista de lectura.  
  
13. En el cuadro de diálogo lista de lectura, haga clic en **devolver parámetros** y haga clic en **EMPNO** en los elementos de origen de datos. Haga clic en el **se asignan a identificador**.  
  
14. Haga clic en **finalizar** en el cuadro de diálogo lista de lectura.  
  
15. Guarde el nuevo origen de datos externo escribiendo **Ctrl + s**.  
  
#### <a name="test-the-external-data-source-connection"></a>Probar la conexión del origen de datos externos  
  
1.  En el nuevo sitio web, haga clic en el **crear listas y formularios** botón. Aparece la lista de crear y formulario de cuadro de diálogo OracleEMP.  
  
2.  Escriba **OracleEMP_List** para el nombre de la lista y haga clic en el **Aceptar** botón.  
  
3.  Una vez que se crea la lista, haga clic en el **vista resumen** botón en el menú.  
  
4.  Haga clic en **OracleEMP_List** en listas externas.  
  
5.  Haga clic en el **vista previa en el explorador** botón en el menú para probar la operación ReadList del adaptador.  
  
## <a name="troubleshoot"></a>Solucionar problemas
  
-   En equipos de 64 bits debe asegurarse de que también se instalan los componentes de cliente de Oracle de 32 bits. Esto es porque se ejecutará como un proceso de 32 bits que requieren acceso a los componentes de 32 bits durante el desarrollo de Visual Studio y los asistentes de TI.