---
title: Configurar el inicio de sesión en las credenciales para el Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e29f79830a3b76c094ebf8b70d533bfd36218f95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223196"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a>Configurar el inicio de sesión en las credenciales para el Siebel
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] requiere que los clientes de adaptador proporcionar las credenciales del cliente. El adaptador utiliza estas credenciales para autenticar al usuario con el sistema Siebel y para establecer una conexión.  
  
 Los clientes de adaptador pueden proporcionar el cliente las credenciales en tiempo de diseño o en tiempo de ejecución. En tiempo de diseño, se necesitan credenciales para generar los metadatos. En tiempo de ejecución, se necesitan credenciales para realizar operaciones en el sistema Siebel. Esta sección proporciona información acerca de cómo especificar las credenciales del cliente en tiempo de diseño y tiempo de ejecución.  
  
## <a name="enter-the-client-credentials-at-design-time"></a>Escriba las credenciales del cliente en tiempo de diseño  
 Para tiempo de diseño, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a>Escriba las credenciales del cliente mediante el complemento Consume Adapter Service  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Plantillas**|Haga clic en **Consume Adapter Service**.|  
  
3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  
  
4.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a>Escriba las credenciales del cliente mediante el Asistente para agregar metadatos de adaptador  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **agregar adaptador**.|  
    |**Plantillas**|Haga clic en **agregar metadatos de adaptador**.|  
  
3.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
4.  En el Asistente para agregar adaptador, seleccione **WCF-Siebel**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  
  
    > [!IMPORTANT]
    >  Si ya tiene un puerto de WCF-Siebel configurado en BizTalk, seleccione el puerto de la **puerto** lista.  
  
5.  Haga clic en **Siguiente**.  
  
6.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
7.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="enter-client-credentials-at-run-time"></a>Escriba las credenciales del cliente en tiempo de ejecución  
 Para el tiempo de ejecución, debe especificar las credenciales del cliente como parte de la configuración del puerto WCF-Custom o WCF-Siebel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
#### <a name="enter-credentials-for-the-wcf-custom-port"></a>Escriba las credenciales para el puerto de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** . En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4.  Para un puerto de envío en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de ESSO.  
  
5.  Haga clic en **Aceptar**.  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]También es compatible con el sistema de inicio de sesión único (ESSO) empresarial. Solo es aplicable en el escenario de BizTalk, en el que el adaptador de WCF es consciente de las aplicaciones afiliadas ESSO ESSO. Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).
  
#### <a name="enter-credentials-for-the-wcf-siebel-port"></a>Escriba las credenciales para el puerto de WCF-Siebel  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** . En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4.  En el cuadro de diálogo de propiedades de puerto de la **tipo** la lista desplegable, seleccione el puerto de WCF-Siebel que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
5.  Para un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de ESSO.  
  
6.  Haga clic en **Aceptar**.  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]También es compatible con el sistema de inicio de sesión único (ESSO) empresarial. Solo es aplicable en el escenario de BizTalk, en el que el adaptador de WCF es consciente de las aplicaciones afiliadas ESSO ESSO. Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)