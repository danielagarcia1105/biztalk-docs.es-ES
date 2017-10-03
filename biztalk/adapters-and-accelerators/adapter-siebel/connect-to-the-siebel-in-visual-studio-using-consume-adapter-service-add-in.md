---
title: Conectarse al sistema Siebel en Visual Studio mediante Consume Adapter Service complemento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2baaa361-1b14-4d00-bcef-f68bc3fa7139
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea8cc3ec9df24cfa2eba5859bf1baa69b3da17f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-consume-adapter-service-add-in"></a>Conectarse al sistema Siebel en Visual Studio mediante Consume Adapter Service complemento
El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] se instala al instalar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] carga todos los enlaces de WCF-Custom instalados en el equipo. Para conectarse a un sistema de Siebel mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en un proyecto de BizTalk, debe utilizar el **siebelBinding**.  
  
## <a name="connecting-to-a-siebel-system-using-consume-adapter-service-add-in"></a>Conectarse a un sistema Siebel mediante Consume Adapter Service complemento  
 Realice los pasos siguientes para conectarse a un sistema Siebel mediante el [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)].  
  
#### <a name="to-connect-to-a-siebel-system"></a>Para conectarse a un sistema Siebel  
  
1.  Para conectarse mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] en una solución de BizTalk:  
  
    1.  Crear un proyecto de BizTalk mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
    3.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Categorías**|Haga clic en **Consume Adapter Service**.|  
        |**Plantillas**|Haga clic en **Consume Adapter Service**.|  
  
    4.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
2.  Desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
3.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario**.  
  
4.  Especifique el nombre de usuario y la contraseña para conectarse al sistema Siebel.  
  
5.  Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear la conexión del sistema Siebel URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
    > [!NOTE]
    >  Si los parámetros de conexión contienen caracteres reservados, debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
6.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, requeridos por las operaciones de destino. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
7.  Haga clic en **Aceptar**.  
  
8.  Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión.  
  
     ![Utilizar el servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
     La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los distintos nodos que contiene varias operaciones que pueden realizarse en el sistema Siebel. Por ejemplo, el **objetos comerciales** nodo contiene todos los objetos de negocios y los componentes empresariales que se pueden invocar en el sistema Siebel. De forma similar, el **servicios empresariales** nodo contiene todos los servicios de negocios en el sistema Siebel conectado a. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).