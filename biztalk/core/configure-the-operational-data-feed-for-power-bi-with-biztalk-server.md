---
title: Habilitar Power BI | Documentos de Microsoft
description: Instalar la plantilla de Power BI en Feature Pack de BizTalk Server
ms.custom: fp1
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88b036aaeb50c2997e1c6b49ae1788a488be1b1a
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a>Configurar los datos operativos de Power BI de la fuente en el servidor BizTalk Server

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , enviar seguimiento a Power BI mediante la plantilla de Power BI proporcionan o crear los suyos propios. 

## <a name="what-is-operational-data"></a>¿Qué es datos operativos
Datos operativos están obtener información acerca de las instancias y los mensajes que fluyen a través de su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno. La fuente de datos operativos es los mismos datos que desea obtener en el concentrador de grupo en [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]. Los datos se tiene acceso y consultan mediante herramientas de visualización, incluidos los Power BI. 

La fuente incluye las siguientes tablas de datos:
* Datos de aplicación
* AS2 Registros de estado
* Información de procesamiento por lotes
* Información de instancia
* Registros de agregaciones del intercambio
* Registros de estado de intercambio
* Mensajes
* Suscripciones
* Eventos de seguimiento
* Informes de las transacciones
* Conjuntos de transacciones

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com) es un excelente recurso para comprender y aprender más acerca de Power BI.

## <a name="prerequisites"></a>Requisitos previos
* Descargue e instale [Power BI Desktop](https://powerbi.microsoft.com/desktop/) en cualquier equipo que tenga acceso a la red a la[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado. Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md). Confirme que IIS está instalado, abra **Administrador de Internet Information Services**. 
* Opcional. Instalar y configurar un [Power BI Gateway](https://powerbi.microsoft.com/gateway/) conectar [PowerBI.com](http://powerbi.microsoft.com) con el servidor de BizTalk local. Si no está utilizando un servidor de BizTalk local, es necesario la puerta de enlace.

## <a name="step-1-enable-operational-data"></a>Paso 1: Habilitar datos operativos

1. Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**). 
2. Vaya a la carpeta de instalación de BizTalk (por ejemplo, escriba: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).
3. En el siguiente texto, reemplace `Default Web Site`, `operationalDataServiceAppPool`, `domain\user`, `password`, y `domain\group` con sus valores:

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>, <domain>\<user>, <domain>\<user2>'
    ```

    * **Servicio**: el servicio esté configurado (**OperationalData** para Power BI)
    * **WebSiteName**: el sitio web IIS existente que hospeda el servicio. El valor predeterminado es **Default Web Site**.
    * **ApplicationPool**: el grupo de aplicaciones utilizada por el servicio. Si existe, no se crea uno nuevo. El valor predeterminado es **DefaultAppPool**.
    * **ApplicationPoolUser**: configura el grupo de aplicaciones para que se ejecute como esta identidad de usuario. Debe tener un operador de BizTalk Server o privilegios más altos.
    * **ApplicationPoolUserPassword**: contraseña para el ApplicationPoolUser
    * **AuthorizationAccount**: lista de grupos o usuarios que pueden usar este servicio de autorizados

    En el ejemplo siguiente, se utiliza el `Default Web Site`, cree un grupo de aplicaciones denominado `PowerBIAppPool`, ejecute el grupo de aplicaciones como el `bootcampbts2016\btsservice` , utilice `BIZTALK-serviceacct` como la contraseña de la cuenta de usuario y otorgar el `BizTalk Server Administrators` permisos del grupo. No olvide escriba lo siguiente, incluido el único proporciona los valores que lo rodea con espacios: 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    Cuando haya finalizado, se crea la aplicación BizTalkOperationalDataService en IIS:  
    ![Aplicación de BizTalkMOperationalDataServer](../core/media/biztalkmanagementservice-apppool.png)


4. Para confirmar que funciona, vaya a `http://localhost/BizTalkOperationalDataService`. 

    Si se le pedirá al inicio de sesión, inicie sesión con una cuenta que sea miembro de la domain\group que escribió en el paso anterior (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`). 

    Si se le pide que abra o guarde BizTalkOperationalDataService.json, completa la instalación. Puede guardarlo localmente y, a continuación, ábralo en el Bloc de notas o Visual Studio para ver el contenido. 

> [!WARNING]
> La aplicación BizTalkOperationalDataService en IIS usa un archivo web.config. Elementos en el archivo web.config **distinguen mayúsculas de minúsculas**. Por tanto, cuando se ejecuta la secuencia de comandos de Windows PowerShell, asegúrese de escribir las mayúsculas y minúsculas correctas para `-AuthorizationRoles` valor. Si no está seguro del caso, aquí es una manera fácil de averiguar: 
> 
> 1. Abra **administración de equipos**y expanda **usuarios y grupos locales**.
> 2. Seleccione **grupos**y desplácese hacia abajo hasta la **SQLServer...** grupos. 
> 3. En el ejemplo siguiente, observe **BOOTCAMPBTS2016** esté en mayúsculas. Si ve todo en mayúsculas, a continuación, escriba el nombre del equipo en todo en mayúsculas. 
> 
> ![Nombre del equipo está en mayúsculas](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a>Paso 2: Usar la plantilla en Power BI

1. Descargue e instale el [Power BI Desktop](https://powerbi.microsoft.com/desktop/) en el servidor BizTalk Server. Puede seleccionar para abrirlo, que es opcional. Si tiene una cuenta profesional o educativa, puede tener acceso a Power BI. Pruebe a iniciar sesión con esa cuenta. O bien, puede probarlo de forma gratuita después de suscribirse. 
2. Abra la `\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService` carpeta y abra el `BizTalkOperationalData.pbit` archivo:  
![Pbit abrir archivo](../core/media/operational-data-pbit.png)

3. Escritorio de Power BI se abre y se le pedirá una dirección URL. Escriba el `http://localhost/<yourWebSite>` dirección URL que ha creado para la fuente de OData. Por ejemplo, escriba `http://localhost/BizTalkOperationalDataService`. La dirección URL tiene un aspecto similar al siguiente:  
![Escriba la dirección URL](../core/media/operational-data-url.png)

4. Seleccione **carga**. La ventana de carga y se conecta a las fuentes de oData diferentes en el archivo BizTalkOperationalDataService.json. Cuando se complete, el panel muestra detalles acerca de su entorno.

## <a name="couldnt-authenticate"></a>No se pudo autenticar
Si obtiene `couldn't authenticate with the credentials provided` mensaje similar al siguiente, es posible que la identidad del grupo de aplicaciones no tiene suficiente acceso a las bases de datos de BizTalk Server. Puede cambiar la identidad del grupo de aplicaciones en IIS para una cuenta con más privilegios, puede ser la cuenta de usuario con sesión iniciada (que tiene privilegios de administrador local). 

![No se pudo autenticar con las credenciales proporcionadas](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a>Llevar a cabo más
Esto es sólo el principio. Power BI también tiene una puerta de enlace que se puede instalar en un servidor de BizTalk local. Con la puerta de enlace, puede publicar el panel, obtener datos en tiempo real y crear una programación para actualizar el panel. En el blog siguiente es excelente para que detalla estos pasos: 

* [Cómo publicar datos operativos de BizTalk en Power BI – configuración paso a paso](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

El [aprendizaje guiado](https://powerbi.microsoft.com/guided-learning/) también es un buen lugar para obtener más información acerca de Power BI y todas las cosas que puede hacer. 

## <a name="see-also"></a>Vea también

[Más información acerca de Power BI](https://www.powerbi.com)  
[Configurar el Feature Pack](../core/configure-the-feature-pack.md)
