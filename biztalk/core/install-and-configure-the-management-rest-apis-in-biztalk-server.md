---
title: Instalar y configurar las API de REST de administración | Microsoft Docs
description: Consultar los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack en BizTalk Server
ms.custom: fp1
ms.date: 02/25/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828569"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>Instalar y configurar las API de REST de administración de BizTalk Server

## <a name="what-are-management-data-apis"></a>¿Cuáles son los datos de administración de API
Datos de administración de API son puntos de conexión que le permiten actualizar, agregar y consultar el estado de los diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno. Los puntos de conexión se agregan mediante REST y viene acompañado de una definición de swagger. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger. Estas API facilitan las llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más. 

Para ver las API disponibles y qué puede hacer, consulte [referencia de API de REST de característica Pack](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016).

## <a name="prerequisites"></a>Requisitos previos
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. Confirme que IIS está instalado en el servidor BizTalk Server, abra **Administrador de Internet Information Services**. 

  En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado. Consulte [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md). 

## <a name="step-1-install-the-rest-apis"></a>Paso 1: Instalar las API de REST

1. Ejecutar Windows PowerShell como administrador (**iniciar** menú > tipo **PowerShell** > haga clic en > **ejecutar como administrador**). 
2. Vaya a la carpeta de instalación de BizTalk (por ejemplo, escriba: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).
3. En el siguiente texto y reemplace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, y `domain\group` con sus valores:

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    En el ejemplo siguiente, usamos el `Default Web Site`, cree un grupo de aplicaciones denominado `RESTAppPool`, ejecutar el grupo de aplicaciones como la `bootcampbts2016\btsservice` cuenta, use `BIZTALK-serviceacct` como la contraseña de la cuenta de usuario y otorgar permisos de grupo de administradores de BizTalk Server. Asegúrese de escribir lo siguiente, incluida la única proporciona los valores que lo rodea con espacios: 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    Cuando haya finalizado, el **BizTalkManagementService** aplicación se crea dentro de IIS:  
    ![Aplicación BizTalkManagementService](../core/media/biztalkmanagementservice-apppool.png)

4. Para confirmar que funciona, vaya a `http://localhost/BizTalkManagementService/swagger`. Si le pedirá que inicie sesión, inicie sesión con una cuenta que sea miembro de la domain\group que escribió en el paso anterior (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`). 

> [!WARNING]
> La aplicación BizTalkManagementService en IIS usa un archivo web.config. Elementos dentro de web.config **distinguen mayúsculas de minúsculas**. Por lo que al ejecutar el script de Windows PowerShell, asegúrese de escribir las mayúsculas y minúsculas correctas para `-AuthorizationRoles` valor. Si no está seguro del caso, aquí es una manera fácil de averiguar: 
> 
> 1. Abra **administración de equipos**y expanda **usuarios y grupos locales**.
> 2. Seleccione **grupos**y desplácese hacia abajo hasta la **SQLServer...** grupos. 
> 3. En el ejemplo siguiente, observe **BOOTCAMPBTS2016** está en mayúsculas. Si ve todo en mayúsculas, a continuación, escriba el nombre del equipo en todo en mayúsculas. 
> 
> ![Nombre del equipo está en mayúsculas](../core/media/groups-case.png)

Ahora que las API de REST se exponen a través de IIS, puede obtener acceso y ejecutadas por otras aplicaciones. [Referencia de API de REST de paquete de características](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016) enumera las API.

Puede cambiar quién tiene acceso mediante la actualización manualmente el **web.config** archivo, que se encuentra en la carpeta raíz de la aplicación de administración. Por ejemplo, utilice los procedimientos siguientes para permitir que cualquier persona acceso a swagger de salida: 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>Paso 2: Probar las API

1. En el servidor BizTalk Server, vaya a `http://localhost/BizTalkManagementService/swagger`.

2. Desplácese a **Hosts**y seleccione **mostrar u ocultar**. Hay un comando GET; Haga clic en esta fila:  
![OBTENER todos los hosts](../core/media/managment-rest-apis-hosts-get.png)

3. Muestra los detalles. Seleccione **Pruébelo**:  
![Pruébelo](../core/media/managment-rest-apis-hosts-tryitout.png)

4. El cuerpo de respuesta devuelve todos los hosts:  
![Respuestas](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> Si examina `http://localhost/BizTalkManagementService`, obtendrá un error 500. Eso es bueno. Basta con agregar `/swagger` al final de la dirección URL y verá la API de REST disponibles. 


## <a name="see-also"></a>Vea también
 [Configuración del Feature Pack](../core/configure-the-feature-pack.md)