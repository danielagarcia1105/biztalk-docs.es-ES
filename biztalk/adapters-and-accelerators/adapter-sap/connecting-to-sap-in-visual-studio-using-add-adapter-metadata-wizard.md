---
title: Conectarse a SAP en Visual Studio mediante metadatos de Asistente para agregar adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a442837b-e7d8-4edb-9c5e-5603d4c58fe5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f56b5035787587e429614749cbfb0c1091b72c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a>Conectarse a SAP en Visual Studio mediante metadatos de Asistente para agregar adaptador
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se expone como un adaptador de BizTalk y por lo tanto, puede usar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para las operaciones que desea realizar en un sistema SAP mediante el adaptador.  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a>Conectarse a un sistema SAP usando metadatos Asistente para agregar adaptador  
 Realice los pasos siguientes para conectarse a un sistema SAP mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
#### <a name="to-connect-to-an-sap-system"></a>Para conectarse a un sistema SAP  
  
1.  Para conectarse mediante la [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en una solución de BizTalk:  
  
    1.  Crear un proyecto de BizTalk mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
    2.  Haga clic en el nombre del proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
    3.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Categorías**|Haga clic en **agregar adaptador**.|  
        |**Plantillas**|Haga clic en **agregar metadatos de adaptador**.|  
  
    4.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
    5.  En el Asistente para agregar adaptador, seleccione **WCF SAP**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  
  
        > [!IMPORTANT]
        >  Si ya tiene un puerto de SAP de WCF configurado en BizTalk, seleccione el puerto de la **puerto** lista.  
  
    6.  Haga clic en **Siguiente**.  
  
2.  Desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding** y haga clic en **configurar**.  
  
3.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  
  
    > [!IMPORTANT]
    >  Si usas la biblioteca de conexión de red segura de SAP (SNC) para conectarse a un sistema SAP, no especifique un nombre de usuario y una contraseña.  
  
4.  Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
    > [!IMPORTANT]
    >  Si está utilizando la biblioteca de SAP SNC para conectarse a un sistema SAP, establecer el **UseSnc** propiedad de conexión en **True**.  
  
    > [!NOTE]
    >  Si los parámetros de conexión contienen caracteres reservados, debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
5.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, requeridos por las operaciones de destino. Por ejemplo, si desea tener como destino de una operación de ReceiveIdoc debe establecer el **ReceiveIdocFormat** enlaza la propiedad de cadena. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    > [!NOTE]
    >  Si va a generar los metadatos que utilizan [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] y ha seleccionado un puerto de envío WCF-SAP existente, no es necesario especificar las propiedades de enlace. Las propiedades de enlace se toman de la configuración del puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si los hubiera. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución se pueden aplicables los valores especificados para propiedades de enlace en la configuración del puerto de envío.  
  
    > [!IMPORTANT]
    >  Si está utilizando la biblioteca de SAP SNC para conectarse a un sistema SAP, establecer el **SncLibrary** y **SncPartnerName** en los valores adecuados.  
    >   
    >  El **SncLibrary** enlaza la propiedad toma la ruta de acceso y el nombre de archivo de los archivos DLL necesarios para que usar SNC para conectarse a un sistema SAP. Estas DLL deben estar presentes en el equipo con el cliente SAP y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] instalado. Para obtener más información, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación disponible en \<Guía de instalación >: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
    >   
    >  El **SncPartnerName** enlaza la propiedad toma el nombre SNC del asociado de comunicación.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el misma para el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
     ![Utilizar el servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
     La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los distintos nodos que contienen varios artefactos que se pueden invocar en un sistema SAP. Por ejemplo, el **RFC** nodo contiene todos los documentos de RFC disponibles en el sistema SAP conectado a. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse al sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)