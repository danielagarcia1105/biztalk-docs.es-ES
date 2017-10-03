---
title: "Cómo crear puertos de envío para PeopleSoft Enterprise | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 374261ce-2cb5-4193-a0a2-658f989b2c60
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b6b5caa44976aec7a4afb8e0eccf5b1f8904111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a>Creación de puertos de envío para PeopleSoft Enterprise
Siga estos pasos para crear un puerto de envío mediante la consola de administración de BizTalk Server.  
  
## <a name="creating-a-send-port"></a>Crear un puerto de envío  
  
#### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
    6.  Haga clic en **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de PeopleSoft** diálogo cuadro, realice lo siguiente:  
  
    1.  Expanda **propiedades de adaptador necesarias**y escriba **ruta de acceso de servidor de aplicación**, **JAVA_HOME**, **nombre de usuario**,  **contraseña**y el archivo Jar para la conexión en el sistema Peoplesoft.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema PeopleSoft.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de envío de PeopleSoft](../core/creating-peoplesoft-send-handlers.md)