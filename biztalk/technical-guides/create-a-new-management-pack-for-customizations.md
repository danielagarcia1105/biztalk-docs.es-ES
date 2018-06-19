---
title: Crear un nuevo módulo de administración para personalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ce1ffa0-57c7-41ce-b459-48c36522889e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d04b29cd96a66057d83b5212472f0ea69150f0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297596"
---
# <a name="create-a-new-management-pack-for-customizations"></a>Crear un nuevo módulo de administración para personalizaciones
Mayoría de los módulos de administración de proveedores está sellada por lo que no se puede cambiar la configuración original en el archivo de módulo de administración. No obstante, puede crear personalizaciones, como invalidaciones o nuevos objetos de supervisión, y guardarlos en un módulo de administración distinto. De forma predeterminada, Operations Manager 2007 R2/2012 guarda todas las personalizaciones en el módulo de administración predeterminado. Como práctica recomendada, en su lugar, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar.  
  
 La creación de un nuevo módulo para almacenar invalidaciones tiene las siguientes ventajas:  
  
-   Simplifica el proceso de exportación de personalizaciones que se crearon en los entornos de prueba y preproducción para el entorno de producción. Por ejemplo, en lugar de exportar el módulo de administración predeterminado que contiene las personalizaciones de varios módulos de administración, puede exportar únicamente el módulo de administración que contiene las personalizaciones de un solo módulo de administración.  
  
-   Puede eliminar el módulo de administración original sin tener que eliminar el módulo de administración predeterminado primero. Un módulo de administración que contiene personalizaciones depende el módulo de administración original. Esta dependencia requiere que elimine el módulo de administración con las personalizaciones antes de que pueda eliminar el módulo original. Si todas las personalizaciones se guardan en el módulo de administración predeterminado, debe eliminar el módulo de administración predeterminado antes de poder eliminar un módulo de administración original.  
  
-   Es más fácil hacer un seguimiento y actualizar personalizaciones en módulos de administración individuales.  
  
 Para obtener más información sobre sellados y módulos de administración sin sellar, consulte [Management Pack Formats](http://go.microsoft.com/fwlink/?LinkID=198193) (http://go.microsoft.com/fwlink/?LinkId=198193). Para obtener más información acerca de las personalizaciones del módulo de administración, consulte [personalizar los módulos de administración](http://go.microsoft.com/fwlink/?LinkID=198194) (http://go.microsoft.com/fwlink/?LinkID=198194).