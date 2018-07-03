---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador de Siebel en BizTalk | Microsoft Docs
description: Creación de envío WCF-custom y puertos de recepción para usar el adaptador de aplicaciones Siebel eBusiness en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6d9e9cea34a9bfd95765ad4d37f51fcf55f4ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017993"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a>Configurar un puerto mediante el adaptador WCF-custom y el adaptador de Siebel
En este tema proporciona instrucciones sobre cómo configurar WCF-Custom puertos de envío para realizar operaciones de salida en un sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a>Implementación de adaptadores para enviar mensajes a un sistema de Siebel  
 Realice los pasos siguientes para configurar un puerto de envío WCF-Custom para enviar mensajes a un sistema de Siebel mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
4. Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema Siebel.  
  
5. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
6. Desde el **tipo** lista desplegable, seleccione **WCF-Custom** y haga clic en **configurar**.  
  
7. En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
   1. Haga clic en el **General** ficha y, en el **dirección (URI)** campo para especificar el URI de conexión para conectarse a un sistema Siebel. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción para invocar la operación de inserción en el componente de negocio de la cuenta es:  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. Haga clic en el **enlace** pestaña y desde el **BindingType** lista desplegable, seleccione **siebelBinding**. También puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
   4. Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  
  
      - Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.  
  
      - Seleccione el **Use Single Sign-On** opción y especifique una aplicación de afiliado ESSO.  
  
        Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).  
  
   5. Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
8. Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
9. Si eligió un puerto de envío unidireccional estático en el paso 4, especifique una canalización de envío. Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
10. Si eligió un puerto de petición-respuesta estático en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)