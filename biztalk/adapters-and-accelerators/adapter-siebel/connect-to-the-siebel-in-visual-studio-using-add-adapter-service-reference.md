---
title: Conectarse al sistema Siebel en Visual Studio mediante Agregar referencia de servicio de adaptador complemento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d27121be-6407-4bb6-acb5-37dc8a3785c0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdf3ea907ba5905965188d17b3a7493788ef123e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991349"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>Conectarse al sistema Siebel en Visual Studio mediante Agregar referencia de servicio de adaptador complemento
Para conectarse a un sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en una solución de programación. NET, se debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Este tema proporciona instrucciones sobre cómo usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a>Conectarse a un sistema de Siebel mediante Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para conectarse a un sistema de Siebel mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-connect-to-a-siebel-system"></a>Para conectarse a un sistema de Siebel  
  
1. Para conectarse mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] en una solución de BizTalk:  
  
   1. Cree un proyecto de BizTalk con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
   2. Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **Add Adapter Service Reference**. Se abrirá [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
2. Desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
3. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario**.  
  
4. Especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.  
  
5. Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
   > [!NOTE]
   >  Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
  
6. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
7. Haga clic en **Aceptar**.  
  
8. Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el misma para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    ![Consumo de servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
    La [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] muestra los diferentes nodos que contiene las distintas operaciones que se pueden realizar en el sistema Siebel. Por ejemplo, el **objetos de negocios** nodo contiene todos los objetos de negocios y los componentes empresariales que se pueden invocar en el sistema Siebel. De forma similar, el **servicios empresariales** nodo contiene todos los servicios de negocios en el sistema de Siebel es conectado. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).