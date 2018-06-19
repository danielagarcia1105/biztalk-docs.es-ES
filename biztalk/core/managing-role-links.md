---
title: Administrar vínculos de rol | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f85bfe0d16b3963b0ba18585220f508f679346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262636"
---
# <a name="manage-role-links"></a>Administrar vínculos de función

## <a name="overview"></a>Información general
Esta sección proporciona instrucciones sobre el uso de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar vínculos de rol en una aplicación de BizTalk. Un vínculo de rol define la relación entre entidades implicadas en una transacción empresarial, y especifica los tipos de puerto y mensaje utilizados en ambas direcciones de la interacción. Para obtener información general sobre los vínculos de rol, consulte [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).  

## <a name="added-to-application"></a>Agrega a la aplicación  
 Los vínculos de rol se generan en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk. No es posible agregar vínculos de rol a una aplicación de forma individual; un vínculo de rol se agrega a una aplicación del modo que se especifica a continuación:  
  
-   Al agregar un ensamblado de BizTalk que contiene un vínculo de función a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
-   Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un vínculo de función, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
-   Cuando un programador implementa en una aplicación un ensamblado que contiene un vínculo de función de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  

## <a name="deploy-to-production"></a>Implementar en producción  
 El programador de aplicaciones de BizTalk crea vínculos de rol para implementar las comunicaciones entre dos o más entidades implicadas en una transacción empresarial (como, por ejemplo, su empresa y un proveedor). El programador no tiene que especificar necesariamente las entidades implicadas en la transacción, sino solo sus roles. Para implementar una aplicación que incluye un vínculo de rol en un entorno de producción y habilitar la comunicación real entre las entidades, es preciso efectuar la configuración siguiente, tal y como se describe en esta sección:  
  
-   Si no se llevó a cabo durante el proceso de desarrollo, se debe asignar una entidad a cada uno de los roles definidos en el vínculo de rol. Esta acción se denomina "dar de alta" una entidad para un rol. Posteriormente, podrá dar de baja la entidad si no desea que ésta siga teniendo el rol asignado.  
  
-   Los puertos lógicos de cada una de las entidades definidas en el vínculo de rol deben estar enlazadas a los puertos físicos de las instancias de host de BizTalk que alojarán la aplicación.  
  
 Para obtener más información sobre el desarrollo de vínculos de función, vea [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
## <a name="next-step"></a>Paso siguiente
  
-   [Cómo dar de alta o baja a una entidad para un rol](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)