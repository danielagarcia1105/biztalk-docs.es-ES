---
title: "Instalar y configurar las API de REST de administración | Documentos de Microsoft"
description: "Consultar los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack en BizTalk Server"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c207b0aca5f2673e615167f75f7f1c7c3fb0e042
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>Instalar y configurar las API de REST de administración de BizTalk Server

## <a name="what-are-management-data-apis"></a>¿Cuáles son los datos de administración de API
API de datos de administración son puntos de conexión que pueden actualizar, agregar y consultar el estado de diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno. Los puntos de conexión se agregan con REST y vienen con una definición de swagger. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger. Estas API realizan llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más. 

## <a name="prerequisites"></a>Requisitos previos
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado. Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md). Confirme que IIS está instalado en el servidor de BizTalk abriendo **Administrador de Internet Information Services**. 

## <a name="step-1-install-the-rest-apis"></a>Paso 1: Instalar la API de REST

1. Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**). 
2. Vaya a la carpeta de instalación de BizTalk (por ejemplo, escriba: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).
3. En el siguiente texto, reemplace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, y `domain\group` con sus valores:

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    En el ejemplo siguiente, se utiliza el `Default Web Site`, cree un grupo de aplicaciones denominado `RESTAppPool`, ejecute el grupo de aplicaciones como el `bootcampbts2016\btsservice` , utilice `BIZTALK-serviceacct` como la contraseña de la cuenta de usuario y otorgar permisos de grupo de administradores de BizTalk Server. No olvide escriba lo siguiente, incluido el único proporciona los valores que lo rodea con espacios: 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    Cuando haya finalizado, el **BizTalkManagementService** aplicación se crea dentro de IIS:  
    ![Aplicación de BizTalkManagementService](../core/media/biztalkmanagementservice-apppool.png)

4. Para confirmar que funciona, vaya a `http://localhost/BizTalkManagementService/swagger`. Si se le pedirá al inicio de sesión, inicie sesión con una cuenta que sea miembro de la domain\group que escribió en el paso anterior (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`). 

> [!WARNING]
> La aplicación BizTalkManagementService en IIS usa un archivo web.config. Elementos en el archivo web.config **distinguen mayúsculas de minúsculas**. Por tanto, cuando se ejecuta la secuencia de comandos de Windows PowerShell, asegúrese de escribir las mayúsculas y minúsculas correctas para `-AuthorizationRoles` valor. Si no está seguro del caso, aquí es una manera fácil de averiguar: 
> 
> 1. Abra **administración de equipos**y expanda **usuarios y grupos locales**.
> 2. Seleccione **grupos**y desplácese hacia abajo hasta la **SQLServer...** grupos. 
> 3. En el ejemplo siguiente, observe **BOOTCAMPBTS2016** esté en mayúsculas. Si ve todo en mayúsculas, a continuación, escriba el nombre del equipo en todo en mayúsculas. 
> 
> ![Nombre del equipo está en mayúsculas](../core/media/groups-case.png)

Ahora que las API de REST se exponen a través de IIS, puede obtener acceso a y ejecutados por otras aplicaciones. 

Puede cambiar quién tiene acceso mediante la actualización manual del **web.config** archivo, que se encuentra en la carpeta raíz de la aplicación de administración. Por ejemplo, utilice los procedimientos siguientes para permitir que cualquier usuario acceso a la swagger de salida: 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>Paso 2: Probar la API

1. En el servidor BizTalk Server, vaya a `http://localhost/BizTalkManagementService/swagger`.

2. Desplácese a **Hosts**y seleccione **mostrar/ocultar**. Hay un comando GET; Haga clic en esta fila:  
![OBTENER todos los hosts](../core/media/managment-rest-apis-hosts-get.png)

3. Muestra los detalles. Seleccione **Pruébelo**:  
![Pruébelo](../core/media/managment-rest-apis-hosts-tryitout.png)

4. El cuerpo de respuesta devuelve todos los hosts:  
![Respuestas](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> Si llega hasta `http://localhost/BizTalkManagementService`, obtendrá un error 500. Es bueno. Basta con agregar `/swagger` al final de la dirección URL y, verá las API de REST disponible. 


## <a name="see-also"></a>Vea también
 [Configurar el Feature Pack](../core/configure-the-feature-pack.md)