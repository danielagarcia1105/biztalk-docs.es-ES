---
title: "Creación de puertos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d109e102ada04e673fa5eddc3010201b266a150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-ports"></a>Crear puertos
Use los siguientes procedimientos para crear puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el inicio de sesión único.  
  
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
  
## <a name="creating-a-receive-port"></a>Crear un puerto de recepción  
  
#### <a name="to-create-a-receive-port"></a>Para crear un puerto de recepción  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.  
  
3.  En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:  
  
    1.  En el **nombre** , escriba `ReceiveFromTIBCOEMS`.  
  
    2.  En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.  
  
    3.  Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.  
  
4.  En el **ubicaciones de recepción** página, realice lo siguiente:  
  
    1.  Haga clic en **Nueva**.  
  
    2.  En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.  
  
    3.  Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.  
  
    4.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.  
  
    5.  En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.  
  
    6.  Seleccione el **habilitar ventana de servicio** casilla de verificación.  
  
    7.  Haga clic en **Aceptar**.  
  
5.  En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.  
  
6.  En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.  
  
7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)