---
title: Configurar los datos operativos fuentes para Power BI con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a>Configurar la fuente en Power BI con BizTalk Server de datos operativos
Leer datos operativos proporcionados a través de una fuente oData en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , enviar seguimiento a Power BI mediante la plantilla de Power BI proporcionan o crear los suyos propios. 

## <a name="what-is-operational-data"></a>¿Qué es datos operativos
Datos operativos están obtener información acerca de las instancias y los mensajes que fluyen a través de su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno. La fuente de datos operativos es los mismos datos que desea obtener en el concentrador de grupo en el [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] consola. Los datos son accesibles y consultan mediante herramientas de visualización, incluidos los Power BI. 

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
* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado. Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md). 

## <a name="enable-operational-data-feed"></a>Habilitar la fuente de datos operativas

1. Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**). 
2. Vaya a la carpeta donde [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] está instalado **(x86) de archivos de programa/Microsoft BizTalk Server 2016**
3. Ejecute el siguiente comando. Asegúrese de actualizar su `website`, `domain\user`, `password`, y `domain\group` con sus valores: 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. Después de ejecutar la secuencia de comandos, busque la nueva aplicación de IIS:  
    1. Abra el explorador web
    2. Vaya a **http://localhost/BizTalkOperationalDataService**

## <a name="use-the-power-bi-template"></a>Usar la plantilla de Power BI
Para obtener acceso al archivo de plantilla de Power BI y usar la visualización proporcionada de Microsoft, siga estos pasos:

1. Descargue e instale el [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Vaya a la carpeta de servidor BizTalk Server en **(x86) de archivos de programa \Microsoft BizTalk Server 2016\OperationalDataService**.
3. Abra la **BizTalkOperationalData.pbit** archivo.
4. Cuando se le pida desde Power BI, pegue la **http://localhost/\<yourWebSite\>**  dirección URL que ha creado para la fuente de OData. Por ejemplo, escriba **http://localhost/OperationalDataService**. 

    La dirección URL tiene un aspecto similar al siguiente: 
    
    ![Pegue la dirección URL de OData en el archivo de plantilla de Power BI](../core/media/pasteurltopowerbitempaltefile.PNG)

5. Seleccione **carga** para rellenar los campos en el informe de Power BI. 
6. El archivo de plantilla genera automáticamente la información y las tablas disponibles de la fuente de OData.

Los datos operativos se expone a través del equipo, pueden acceder y ejecutados por otras aplicaciones basadas en permisos. 

Para obtener más información sobre Power BI y cómo publicar el informe de online ir a [PowerBI.com](http://powerbi.microsoft.com)

## <a name="see-also"></a>Vea también

[Más información acerca de Power BI](https://www.powerbi.com)  
[Configurar el Feature Pack](../core/configure-the-feature-pack.md)