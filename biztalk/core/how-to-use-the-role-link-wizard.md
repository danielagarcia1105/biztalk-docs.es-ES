---
title: "Cómo usar el Asistente para vínculo de función | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-role-link-wizard"></a>Cómo usar al Asistente para vínculo de función
El Asistente para vínculo de rol permite crear un vínculo de rol nuevo o modificar uno existente. Lo puede usar para establecer o ver el nombre, tipo y restricción de acceso del vínculo de rol, así como para ver el rol de implementaciones y el rol de usos que componen el tipo de vínculo de rol. Para entender cómo funcionan los vínculos de rol, vea [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).  
  
 **Nombre de vínculo de rol**: el nombre de vínculo de función se rellena automáticamente y es el nombre actual de un vínculo de rol existente que está configurando o un nombre generado automáticamente si va a crear un nuevo vínculo de función. En cualquier caso, puede modificar el nombre.  
  
 **Tipo de vínculo de función**: puede seleccionar un tipo de vínculo de rol existente o cree uno nuevo. Tanto si configura un tipo de vínculo de rol nuevo como uno existente, puede especificar cómo participa la orquestación en el servicio.  
  
> [!NOTE]
>  Se recomienda que cree el tipo de vínculo de rol y el tipo de puerto asociado antes de crear el vínculo de rol, de modo que pueda usar un tipo de vínculo de rol existente para la definición del vínculo de rol. Para obtener más información, consulte [cómo crear vínculos de rol en orquestaciones](../core/how-to-create-role-links-in-orchestrations.md).  
  
 **Uso de vínculo de función**: si crea un nuevo vínculo de función, escriba, tanto la implementa y utiliza roles se crean automáticamente para usted. Puede seleccionar el rol que refleje cómo participa la orquestación en el servicio. Tras finalizar los pasos del asistente, puede cambiar el nombre de los identificadores de rol o quitar un rol para acomodar mejor su implementación. Un tipo de vínculo de rol debe contener un ejemplar de uno de los tipos de rol o un ejemplar de cada tipo. Al hacer clic en **Aceptar**, se crean roles sin configurar correspondientes a cada nombre. También puede seleccionar tipos de puerto para los roles en la ventana Tipos.  
  
> [!NOTE]
>  Si invoca el Asistente para configuración de puertos con el fin de crear un tipo de puerto para el tipo de vínculo de rol y desea seleccionar un tipo de puerto definido anteriormente, asegúrese de que las restricciones de acceso del tipo de puerto no entran en conflicto con las restricciones de acceso del tipo de vínculo de rol.  
  
## <a name="see-also"></a>Vea también  
 [Usar vínculos de rol en orquestaciones](../core/using-role-links-in-orchestrations.md)