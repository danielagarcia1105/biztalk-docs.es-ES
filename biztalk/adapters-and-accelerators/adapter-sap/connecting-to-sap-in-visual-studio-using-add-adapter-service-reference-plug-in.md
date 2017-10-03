---
title: Conectarse a SAP en Visual Studio mediante Agregar referencia de servicio de adaptador complemento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05116c2f-08a4-495b-a031-d377e7ca33e0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19dd824322906bdd148b96eb305e88fc35847947
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>Conectarse a SAP en Visual Studio mediante Agregar referencia de servicio de adaptador complemento
Para conectarse a un sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en una solución de programación. NET, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Este tema proporciona instrucciones sobre cómo usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-service-reference-plug-in"></a>Conectarse a un sistema SAP usar Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para conectarse a un sistema SAP mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-connect-to-an-sap-system"></a>Para conectarse a un sistema SAP  
  
1.  Para conectarse mediante la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] en una solución de BizTalk:  
  
    1.  Crear un proyecto en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**. Se abrirá [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
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
  
    > [!IMPORTANT]
    >  Si está utilizando la biblioteca de SAP SNC para conectarse a un sistema SAP, establecer el **SncLibrary** y **SncPartnerName** en los valores adecuados.  
    >   
    >  El **SncLibrary** enlaza la propiedad toma la ruta de acceso y el nombre de archivo de los archivos DLL necesarios para que usar SNC para conectarse a un sistema SAP. Estas DLL deben estar presentes en el equipo con el cliente SAP y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] instalado. Para obtener más información, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación disponible en \<Guía de instalación >: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
    >   
    >  El **SncPartnerName** enlaza la propiedad toma el nombre SNC del asociado de comunicación.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el misma para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
     ![Utilizar el servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
     La [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] muestra los distintos nodos que contienen varios artefactos que se pueden invocar en un sistema SAP. Por ejemplo, el **RFC** nodo contiene todos los documentos de RFC disponibles en el sistema SAP conectado a. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse al sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)