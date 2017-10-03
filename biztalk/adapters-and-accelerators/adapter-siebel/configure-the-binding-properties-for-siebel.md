---
title: Configurar las propiedades de enlace de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26e9e89319a14317113b730adb189f2f17587f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-siebel"></a>Configurar las propiedades de enlace de Siebel
La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento. Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de Visual Studio (tiempo de diseño) y de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración (tiempo de ejecución). En tiempo de diseño, debe especificar las propiedades de enlace para generar esquemas para las operaciones concretas. En tiempo de ejecución, debe especificar las propiedades de enlace como parte del puerto de envío para enviar mensajes al sistema Siebel.  
  
 Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
## <a name="enter-the-binding-properties-at-design-time"></a>Especifique las propiedades de enlace en tiempo de diseño  
 Para tiempo de diseño, debe especificar las propiedades de enlace de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] cuadro de diálogo.  
  
#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>Especifique las propiedades de enlace mediante el complemento Consume Adapter Service  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Plantillas**|Haga clic en **Consume Adapter Service**.|  
  
3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  
  
4.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y haga clic en **configurar**.  
  
5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** ficha y especifique los valores de enlace, si hay alguno, que deben especificarse antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>Especifique las propiedades de enlace mediante el Asistente para agregar metadatos de adaptador  
  
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
  
6.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y haga clic en **configurar**.  
  
7.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** ficha y especifique los valores de enlace, si hay alguno, que deben especificarse antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
    > [!NOTE]
    >  Si ha seleccionado un puerto de envío WCF-Siebel existente, no es necesario especificar las propiedades de enlace. Las propiedades de enlace se toman de la configuración del puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si los hubiera. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución se pueden aplicables los valores especificados para propiedades de enlace en la configuración del puerto de envío.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="enter-binding-properties-at-run-time"></a>Especificar propiedades de enlace en tiempo de ejecución  
 Para el tiempo de ejecución, debe especificar las propiedades de enlace como parte de WCF-Custom o la configuración del puerto WCF-Siebel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>Especifique las propiedades de enlace para el puerto de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** . En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3.  En el **propiedades de puerto** cuadro de diálogo, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
5.  Desde el **BindingType** lista desplegable, seleccione **siebelBinding**.  
  
6.  En el **configuración** , especifique los valores de las propiedades de enlace diferente y haga clic en **Aceptar**.  
  
#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a>Especifique las propiedades de enlace para el puerto de WCF-Siebel  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** . En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4.  En el **propiedades de puerto** cuadro de diálogo, desde el **tipo** la lista desplegable, seleccione el puerto de WCF-Siebel que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar valores para las propiedades de enlace.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)