---
title: "Vínculos de función y el servicio vinculan Roles | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6630b1ad22ba86f3efe8a19409f3b731880c8a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="role-links-and-service-link-roles"></a>Vínculos de rol y roles de vínculo de servicio
A *rol* es una colección de tipos de puerto que utiliza un servicio o implementa un servicio. Una función representa el tipo de interacción que una entidad puede tener con una o muchas orquestaciones. Las funciones proporcionan flexibilidad y facilidad de administración cuando aumenta el número de entidades. Por ejemplo, una orquestación puede que utilice la función de un remitente. El remitente tendría una o dos entidades asociadas con él. Cuando la orquestación decide qué compañía remitente se va a utilizar para enviar un elemento, compara los precios de las entidades de la función del remitente.  
  
 A *tipo de vínculo de rol* es una propiedad que caracteriza la relación entre dos servicios u orquestaciones. Define el papel que desempeña cada servicio en la relación y especifica los tipos de puerto que proporciona cada función.  
  
 Una entidad, o unidad de organización, representa una entidad externa a BizTalk Server que interactúa con una orquestación. En BizTalk Server, cada organización con la que intercambia mensajes está representada por una entidad. Es necesario dar de alta una entidad en una función para definir cómo interactúa.  
  
 Puede implementar o quitar un tipo de vínculo de función cuando está asociado con una orquestación.  
  
## <a name="orchestrations-and-roles"></a>Orquestaciones y funciones  
 Cuando implementa una orquestación que utiliza un tipo de vínculo de función, la base de datos de configuración guarda la función. Puesto que más de una orquestación pueden utilizar una función, la base de datos de administración guarda sólo una copia del tipo de vínculo de función.  
  
 Si el proyecto de BizTalk contiene dos tipos de vínculo de función en distintos archivos de orquestación (.odx) que tienen el mismo nombre y espacio de nombres, el proyecto de BizTalk no se compila.  
  
### <a name="orchestration-removals-that-use-roles"></a>Eliminaciones de orquestaciones que utilizan funciones  
 Puesto que más de una orquestación pueden utilizar un tipo de vínculo de función, cuando anula la implementación de un ensamblado que contiene una orquestación que utiliza una función, la base de datos de administración quita la función sólo en el caso de que ninguna orquestación la esté utilizando.  
  
 Asimismo, la base de datos de administración sólo quita una función si no tiene entidades dadas de alta. Al igual que no puede sobrescribir una función que tenga entidades dadas de alta, no puede quitar una función en la misma situación.  
  
## <a name="see-also"></a>Vea también  
 [Usar vínculos de rol en orquestaciones](../core/using-role-links-in-orchestrations.md)   
 [Artefactos](../core/artifacts.md)