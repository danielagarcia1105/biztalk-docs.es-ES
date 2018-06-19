---
title: Cómo configurar una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, applications
- applications, configuring
ms.assetid: e1cd1efb-e1ea-4344-8e23-668628d6c5a9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888fc0ff78ebac3ac2314fe3106de4b7b6b51f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250284"
---
# <a name="how-to-configure-an-application"></a>Cómo configurar una aplicación
En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para configurar los artefactos de una aplicación, del modo siguiente:  
  
-   Enlazar puertos lógicos y vínculos de rol con entidades y puertos físicos.  
  
-   Asignar orquestaciones al host bajo el que deben ejecutarse.  
  
-   Configurar puertos de envío y recepción, grupos de puertos de envío y ubicaciones de puertos de recepción.  
  
 Si la aplicación no contiene al menos una orquestación, un puerto de envío, un grupo de puertos de envío, un puerto de recepción o una ubicación de recepción, la información de este tema no es aplicable.  
  
 Después de completar esta configuración, podrá iniciar la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
> [!NOTE]
>  También puede configurar artefactos individualmente desde dentro de la aplicación. Para obtener más información sobre cómo configurar artefactos individuales, consulte los vínculos al final de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-an-application"></a>Para configurar una aplicación  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, haga clic en la aplicación y, a continuación, haga clic en **configurar**.  
  
3.  En el **orquestaciones** lista en el panel izquierdo, haga clic en una orquestación, configurar las propiedades tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**. Si no hay ninguna orquestación en esta aplicación, el **orquestaciones** no mostrar la lista.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Host**|En la lista desplegable, seleccionar un host en el que dar de alta la aplicación.|  
    |**Enlaces - puertos lógicos de entrada**|Mostrar el nombre de un puerto lógico de entrada. Los puertos lógicos se encuentran en las superficies para el puerto de las orquestaciones.|  
    |**Enlaces - puertos de recepción**|Seleccionar el puerto de recepción físico que desea enlazar con el puerto lógico de entrada en la lista desplegable. Esa lista incluye los puertos de la aplicación actual y los de aquellas a las que se haga referencia.|  
    |**Enlaces - puertos lógicos de salida**|Mostrar el nombre de un puerto lógico de salida. Los puertos lógicos se encuentran en las superficies para el puerto de las orquestaciones.|  
    |**Enlaces - grupos de puertos de envío y puertos de envío**|Seleccionar el puerto de envío o el grupo de puertos de envío que desea enlazar con el puerto lógico de salida correspondiente en la lista desplegable. Esa lista incluye los puertos de la aplicación actual y los de aquellas a las que se haga referencia.|  
  
4.  En el **mensajería** lista en el panel izquierdo, haga clic en **puertos de envío y grupos de puertos de envío**, configurar las propiedades tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**. La lista muestra todos los puertos de envío y grupos de puertos de envío de la aplicación actual.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nuevo**|Crear un puerto de envío o un grupo de puertos de envío. Opciones de puertos de envío son idénticos a las opciones disponibles cuando hace clic en el **puertos de envío** nodo en el árbol de consola y seleccione **nuevo**. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Consulte también [cómo crear un grupo de puertos de envío](../core/how-to-create-a-send-port-group.md).|  
    |**Propiedades**|Haga clic en esta opción para ver las propiedades del puerto de envío o grupo de puertos de envío seleccionado. Si selecciona un puerto de envío, el **propiedades de puerto de envío** página muestra, donde puede configurar el puerto. Si selecciona un grupo de puertos de envío, el **propiedades de grupos de puertos de envío** página muestra, donde puede configurar el grupo de puertos de envío. Para obtener más información acerca de cómo configurar propiedades, vea [administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md).|  
    |**Nombre**|Mostrar el nombre de los puertos de envío físicos.|  
    |**Filter**|Mostrar la expresión de filtro aplicada al puerto de envío. Los filtros se configuran en el **propiedades de puerto de envío** ventana.|  
    |**URI**|Mostrar el URI para el puerto seleccionado.|  
  
5.  En el **mensajería** lista en el panel izquierdo, haga clic en **puertos de recepción y ubicaciones**, configurar las propiedades tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**. La lista muestra todos los puertos de recepción y grupos de puertos de recepción de la aplicación actual.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nuevo**|Crear un puerto de recepción nuevo. Opciones de recepción nuevos puertos son idénticos a las opciones disponibles cuando hace clic en el **puertos de recepción** nodo en el árbol de consola y seleccione **nuevo**. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).|  
    |**Propiedades**|Haga clic en esta opción para mostrar las propiedades del elemento seleccionado. Si ha seleccionado un puerto de recepción, el **propiedades de puerto de recepción** página muestra, donde puede configurar el puerto. Si ha seleccionado una ubicación de recepción, el **propiedades de ubicaciones de recepción** página muestra, donde puede configurar la ubicación de recepción. Para seleccionar un puerto de recepción, haga clic en el texto en negrita a la derecha del **puerto de recepción**. Para obtener más información acerca de cómo configurar propiedades, vea [administrar puertos de recepción](../core/managing-receive-ports.md). Consulte también [administrar ubicaciones de recepción](../core/managing-receive-locations.md).|  
    |**Nombre**|Mostrar el nombre de la ubicación de recepción asociada con un puerto de recepción.|  
    |**URI**|Mostrar el URI para la ubicación de recepción seleccionada.|  
  
6.  En el panel izquierdo, haga clic en **vínculos de función**, configurar propiedades que se describen en la tabla siguiente y, a continuación, haga clic en **Aceptar**. Si no hay ningún vínculo de rol en la aplicación, el **vínculos de función** vínculo no se muestra.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dar de alta**|Haga clic para mostrar la **dar de alta entidades** cuadro de diálogo, donde puede seleccionar una entidad que participará en el intercambio definido por el rol.|  
    |**Dar de baja**|Quitar la entidad seleccionada de su participación en el intercambio.|  
    |**Enlazar**|Haga clic en esta opción para establecer una conexión entre el vínculo de rol y los puertos físicos mediante una entidad.|  
    |**Entidad**|Mostrar el nombre de la entidad o entidades que ha dado de alta en este rol.|  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Administrar vínculos de rol](../core/managing-role-links.md)   
 [Administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)   
 [Administrar puertos de recepción](../core/managing-receive-ports.md)   
 [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)