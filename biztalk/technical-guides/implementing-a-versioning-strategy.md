---
title: Implementar una estrategia de control de versiones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a3c7af6-6277-4667-8f14-e6d1cb9e99d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8990fb3d65b29609738ed398829a438478eeabb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015045"
---
# <a name="implementing-a-versioning-strategy"></a>Implementar una estrategia de control de versiones
Control de versiones es el acto de actualización de la implementación de un artefacto e incrementar su número de versión.  
  
## <a name="general-versioning-issues"></a>Problemas generales de control de versiones  
 Control de versiones de aplicación de BizTalk puede ser un problema cuando necesite ejecutar dos versiones de una solución de BizTalk en paralelo, o si no se puede programar el tiempo de inactividad de aplicación de BizTalk para implementar una nueva versión. Si no necesita ejecutar dos versiones de la solución al mismo tiempo (por ejemplo, si tienes que no hay orquestaciones de larga ejecución), es perfectamente aceptable para anular la implementación de la versión antigua e implementar la nueva versión como una estrategia de control de versiones (sin control de versiones de ensamblado). Se trata de una estrategia de control de versiones posibles, aunque recomendamos incrementar el número de versión de archivo (para que sepa qué versión se implementa en los servidores BizTalk Server). Para obtener más información acerca de cómo actualizar una aplicación que se implementa, consulte [lista de comprobación: actualización de un ensamblado](../technical-guides/checklist-updating-an-assembly.md).  
  
 Si necesita compatibilidad con las orquestaciones de larga ejecución, o debe realizar las implementaciones de aplicaciones de BizTalk sin tiempo de inactividad de aplicación de BizTalk, a continuación, una estrategia sólida de control de versiones de BizTalk debe implementarse y practica to-end para los diferentes escenarios de control de versiones. Esto incluye versiones de los ensamblados .NET y control de versiones de todos los artefactos de BizTalk. Esto incluye los esquemas, mapas, canalizaciones, los componentes de canalización, orquestaciones, adaptadores personalizados, las clases personalizado llamado en orquestaciones y mapas, las reglas de negocios y BAM. Para obtener más información acerca de las versiones en paralelo, vea [actualizar usando control de versiones en paralelo](../technical-guides/updating-using-side-by-side-versioning.md).  
  
## <a name="versioning-an-assembly"></a>Control de versiones de un ensamblado  
 Cuando se actualiza un ensamblado, puede optar entre lo siguiente:  
  
- Elegir una versión de ensamblado fija para una entrega determinada e incrementar el número de versión del archivo.  
  
- El incremento de la versión del ensamblado y la versión del archivo durante el desarrollo.  
  
  En la tabla siguiente se comparan estos enfoques:  
  
|**Versión de ensamblado fija, versión del archivo dinámico**|**Versión de ensamblado dinámica, versión de archivo fija o dinámica**|  
|------------------------------------------------------|-----------------------------------------------------------------|  
|Número de versión de ensamblado = Número fijo<br /><br /> Número de versión de archivo = Número de versión de compilación|Número de versión de ensamblado = Número de versión de compilación<br /><br /> Número de versión de archivo = Número de versión de compilación|  
|En tiempo de ejecución de BizTalk Server puede seleccionar la versión incorrecta del ensamblado si hay varios instalados.|BizTalk Server siempre se ejecuta la versión más reciente del ensamblado, incluso si hay varios instalados.|  
|En cualquier momento solo se puede implementar una versión de solución.|Diferentes versiones de la solución se pueden implementar en paralelo (aunque otros aspectos de la solución, como definiciones de esquema, pueden entrar en conflicto).|  
|Debe reiniciarse BizTalk Host para forzar la carga de ensamblados actualizados.|Obliga a BizTalk Server para cargar nuevos ensamblados.|  
|Requiere menos trabajo para crear una implementación nueva ya que no es necesario editar los archivos que hacen referencia al número de versión (por ejemplo, archivos de enlace y perfiles de seguimiento).|Requiere más trabajo para la implementación ya que es necesario mantener actualizados con la versión nueva los archivos que hacen referencia al número de versión del ensamblado.|  
  
 Puede usar la versión de ensamblado fija y el enfoque de la versión de archivo dinámico si es un sistema de creación de prototipos, o bien desarrollar cualquier otro tipo de proyecto que no se publicará. Si no desea entregar la aplicación a un usuario final, puede aumentar la eficacia de las tareas de implementación y reducir las dependencias interrumpidas al fijar la versión de ensamblado e incrementar el número de versión de archivo. Para el seguimiento de versiones, no olvide aumentar el número de versión del archivo de cada compilación.  
  
 Si crea un proyecto que se va a entregar a un usuario final, debería considerar aumentar el número de versión de ensamblado y, de forma opcional, almacenar un número de versión de archivo significativo. Mientras que este enfoque provoca un esfuerzo adicional al tener que modificar los números de versión de compilación y las dependencias asociadas, asegura que se utilizan las últimas versiones de los ensamblados. Al utilizar secuencias de comandos de implementación automatizadas, puede disminuir la influencia del control de versiones. Para ver ejemplos de implementación, consulte [implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](http://go.microsoft.com/fwlink/?LinkId=155134) (<http://go.microsoft.com/fwlink/?LinkId=155134>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
> [!NOTE]  
>  Debe elegir el mecanismo de control de versiones que asegura que los propios archivos se envían y que simplifica el mantenimiento y la mejora.  
  
 Para obtener más información acerca de los problemas de control de versiones, consulte [control de versiones del proyecto de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154209) (<http://go.microsoft.com/fwlink/?LinkID=154209>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.