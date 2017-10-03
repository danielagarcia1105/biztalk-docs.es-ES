---
title: "Instalar y configurar las API de REST de administración | Documentos de Microsoft"
description: "Consultar el estado de los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack 1 de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>Instalar y configurar las API de REST de administración de BizTalk Server
Usar un script de Windows PowerShell para habilitar las API de REST que administrar de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

## <a name="what-are-management-data-apis"></a>¿Cuáles son los datos de administración de API
API de datos de administración son los extremos que pueden actualizar, agregar y consultar el estado de diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno. Los puntos de conexión se agregan con REST y vienen con una definición de Swagger. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger. Estas API realizan llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más. 

En este tema se muestra cómo instalar las API de REST.

## <a name="prerequisites"></a>Requisitos previos
* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado. Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).

## <a name="enable-the-rest-apis"></a>Habilitar las API de REST

1. Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**). 
2. Vaya a la carpeta de BizTalk en **(x86) de archivos de programa/Microsoft BizTalk Server 2016**
3. Ejecute el siguiente comando. Asegúrese de actualizar su `website`, `domain/user`, `password`, y `domain\group` con sus valores: 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. Después de ejecutar la secuencia de comandos, busque la nueva aplicación de IIS:  
    1. Abra el explorador web
    2. Vaya a **http://localhost/OperationalDataService/swagger**

5. Las cargas de las definiciones de Swagger. También puede cambiar quién tiene acceso mediante la actualización de la **web.config** archivo en la carpeta raíz de la aplicación de administración.

Las API de REST se exponen a través de la máquina y se puede obtener acceso a y ejecutadas por otras aplicaciones. 


## <a name="see-also"></a>Vea también
 [Configurar el Feature Pack](../core/configure-the-feature-pack.md)