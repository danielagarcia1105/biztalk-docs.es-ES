---
title: Configurar las propiedades de enlace de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1e2d60ede3e41c08b15d3839f6ece41a68aa373
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989181"
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a>Configurar las propiedades de enlace de Oracle E-Business Suite
La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento. Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar las propiedades de enlace al generar el esquema para operaciones específicas. Desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes de Oracle E-Business Suite.  

 Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

## <a name="specifying-binding-properties-from-visual-studio"></a>Especificar propiedades de enlace desde Visual Studio  
 Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar las propiedades de enlace mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>Para especificar las propiedades de enlace mediante el complemento Consume Adapter Service  

1.  Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique las propiedades de enlace diferente.  

6.  Haga clic en **Aceptar**.  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>Para especificar las propiedades de enlace mediante el Asistente para agregar metadatos de adaptador  

1. Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

4. En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleEBS**. Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de WCF-OracleEBS configurado en BizTalk, seleccione el puerto de la lista de puertos.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  

7. Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que son necesarios antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

   > [!NOTE]
   >  Si ha seleccionado una existente, puerto de envío WCF-OracleEBS, debe no especifique las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En tal caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

8. Haga clic en **Aceptar**.  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>Especificar propiedades de enlace desde la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar las propiedades de enlace como parte de la configuración del puerto WCF-Custom o WCF-OracleEBS.  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>Para especificar las propiedades de enlace para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.  

5. Desde el **BindingType** lista, seleccione **oracleEBSBinding**.  

6. En el **configuración** cuadro, especifique los valores de las propiedades de enlace diferente y, a continuación, haga clic en **Aceptar**.  

#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a>Para especificar las propiedades de enlace para el puerto de WCF-OracleEBS  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador para Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-OracleEBS que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  

   > [!NOTE]
   >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  

## <a name="see-also"></a>Vea también  
 [Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)