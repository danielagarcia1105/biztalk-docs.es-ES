---
title: Archivos de enlace e implementación de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings
- deploying [applications], binding files
- assemblies, binding files
- bindings, applying
- groups, assemblies
- applications, binding files
- binding files, applications
- bindings, hosts
- deploying, assemblies
- updating, assemblies
- assemblies, updating
- hosts, bindings
- binding files, assemblies
- applications, moving
- assemblies, deploying
- binding files, about binding files
- bindings, about bindings
- groups, deploying
- binding files, deploying
- bindings, binding files
ms.assetid: 396ad021-8001-4ed8-8b28-85b72f981fae
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6908f962cd3bb8f9fdec3fcaab6bc131c889da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234068"
---
# <a name="binding-files-and-application-deployment"></a>Archivos de enlace e implementación de la aplicación
En este tema se proporciona información general acerca del uso de archivos de enlace para que la implementación de ensamblados y aplicaciones de BizTalk sea más sencilla. En los siguientes escenarios, podrá ver que los archivos de enlace aceleran la implementación al evitar la necesidad de configurar los enlaces de forma manual:  
  
-   Mover una aplicación desde un entorno de implementación a otro.  
  
-   Actualizar un ensamblado.  
  
-   Implementar un ensamblado para varios grupos de BizTalk.  
  
## <a name="what-is-a-binding"></a>¿Qué es un enlace?  
 Un enlace crea una asignación entre un extremo lógico, como un puerto de orquestación o un vínculo de rol, y un extremo físico, como una entidad o un puerto de envío o recepción. Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk. Puede crear enlaces mediante la consola de administración de BizTalk Server.  
  
## <a name="what-is-a-binding-file"></a>¿Qué es un archivo de enlace?  
 Un archivo de enlace es un archivo .xml que contiene información de enlace para cada orquestación, canalización, asignación o esquema de BizTalk en el ámbito de un ensamblado, aplicación o grupo de BizTalk. El archivo de enlace describe a qué host se enlaza cada orquestación y su nivel de confianza, así como la configuración de cada puerto de envío, grupo de puertos de envío, puerto de recepción, ubicación de recepción y entidad que se ha configurado. Puede generar archivos de enlace y, después, aplicar los enlaces que contienen a un ensamblado, aplicación o grupo para evitar la necesidad de configurar de forma manual enlaces en diferentes entornos de implementación.  
  
## <a name="why-use-binding-files"></a>¿Por qué se usan archivos de enlace?  
 El uso de archivos de enlace puede ser recomendable en los escenarios siguientes.  
  
### <a name="moving-from-one-environment-to-another"></a>Mover desde un entorno a otro  
 Los archivos de enlace se pueden usar para facilitar el movimiento de una aplicación desde un entorno de implementación a otro; por ejemplo, desde un entorno de desarrollo a un entorno de prueba. Esto es así porque  suele ser necesario volver a configurar los enlaces para diferentes entornos de implementación pero al usar archivos de enlace puede evitar realizar repetidamente este paso de configuración manual.  
  
 Una manera de hacerlo consiste en la creación de una biblioteca de enlaces en la que pueda seleccionar al implementar la aplicación a un entorno nuevo. Por ejemplo, puede crear un archivo de enlace para el entorno de prueba y otro para el entorno de producción y, a continuación, agregar ambos a la aplicación. Cuando importe la aplicación al entorno de prueba, puede seleccionar una opción para aplicar los enlaces de prueba. Del mismo modo, cuando importe la aplicación al entorno de producción, puede seleccionar una opción para aplicar los enlaces de producción. De este modo, se evita la necesidad de volver a configurar los enlaces de forma manual para diferentes entornos. Otra manera de hacerlo consiste en importar los enlaces que ha creado para el entorno actual después de importar la aplicación en él. De este modo, los enlaces se aplican de forma automática.  
  
### <a name="updating-an-assembly"></a>Actualizar un ensamblado  
 Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual. Para evitarlo, puede usar un archivo de enlace de la forma siguiente:  
  
-   **Actualizando la misma versión de un ensamblado.** Si el ensamblado tiene puertos enlazados o puertos dinámicos en el primer momento y cambia la configuración de puerto en la consola de administración de BizTalk Server, la configuración se perderá al actualizar el ensamblado con un ensamblado que tenga el mismo número de versión. Puede exportar un archivo de enlace para el ensamblado que va a actualizar. Después de actualizar el ensamblado, puede importarlo a la aplicación y, después, importar su archivo de enlace para volver a aplicar los enlaces anteriores.  
  
-   **Actualizar un ensamblado con una versión más reciente.** Puede exportar un archivo de enlace para el ensamblado que va a actualizar y, después, editarlo para reflejar la nueva versión de ensamblado. Después de importar la nueva versión de ensamblado a la aplicación, puede importar el archivo de enlace a la aplicación para aplicar los enlaces. Para obtener instrucciones sobre cómo editar un archivo de enlace, consulte [personalizar archivos de enlace](../core/customizing-binding-files.md).  
  
### <a name="deploying-an-assembly-to-multiple-biztalk-groups"></a>Implementar un ensamblado para varios grupos de BizTalk  
 Al implementar un ensamblado a varios grupos de BizTalk, puede transportar los enlaces del ensamblado junto con éste. De este modo, se evita la necesidad de configurar por separado los enlaces del ensamblado en cada grupo. Puede hacerlo del modo siguiente:  
  
1.  Cree un archivo de enlace para el ensamblado que va a implementar mediante la exportación de los enlaces del ensamblado.  
  
2.  Agregue el ensamblado y su archivo de enlace a una aplicación. Si va a implementar el ensamblado por separado de otros artefactos, la aplicación puede contener únicamente el ensamblado y el archivo de enlace.  
  
3.  Exporte un archivo .msi para la aplicación y asegúrese de que también selecciona el archivo de enlace para exportarlo.  
  
4.  Importe el archivo .msi de aplicación a los grupos y aplicaciones de BizTalk donde quiera implementarlo. Los enlaces del archivo se aplican de forma automática al ensamblado durante la importación.  
  
## <a name="how-can-i-generate-and-use-binding-files"></a>¿Cómo puedo generar y usar archivos de enlace?  
 Un archivo de enlace no se genera automáticamente para un ensamblado, aplicación o el grupo de BizTalk, pero puede generar un archivo de enlace mediante la exportación de enlaces, tal y como se describe en [exportar enlaces](../core/exporting-bindings6.md). A continuación, puede importar el archivo de enlace a una aplicación o un grupo, como se describe en [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md) y [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md), que automáticamente se aplica sus enlaces.  
  
 Como alternativa, puede agregar el archivo de enlace a una aplicación para que sus enlaces se aplican cuando la aplicación se importa a otro grupo, en lugar de aplicarlos de forma inmediata, como se describe en [cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md). Mediante este último método, puede agregar varios archivos de enlace a una aplicación y, de forma opcional, especificar un entorno de implementación de destino para cada uno de ellos. Al importar la aplicación, a continuación, puede seleccionar que los enlaces que se aplican, según el entorno de implementación de destino, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Mediante este último método, también puede importar archivos de enlace diferentes para los distintos ensamblados de la aplicación.  
  
 Después de generar los archivos de enlace, puede editarlos para cambiar su información de enlace. Para obtener más información, consulte [personalizar archivos de enlace](../core/customizing-binding-files.md).  
  
## <a name="how-are-bindings-applied"></a>¿Cómo se aplican los enlaces?  
 Los enlaces se aplican cuando un archivo de enlace se importa a una aplicación o cuando una aplicación se importa a un nuevo grupo de BizTalk. Cuando se usan archivos de enlace, es importante comprender cómo se enlazan los artefactos a hosts y el orden en el que se aplican los enlaces.  
  
### <a name="binding-to-hosts"></a>Enlace a hosts  
 Cuando los enlaces se exportan por separado o como parte de una aplicación, los hosts y los niveles de confianza se almacenan en el archivo de enlace de la manera siguiente:  
  
-   **Puerto de envío.** Nivel de confianza del host asociado con el controlador de envío.  
  
-   **Ubicación de recepción.** Nivel de confianza del host asociado con el controlador de recepción.  
  
-   **Orquestación.** Nivel de confianza del host.  
  
 Cuando los enlaces se importan a una aplicación o bien una aplicación se importa desde el archivo .msi a un nuevo grupo de BizTalk, se establece la coincidencia de los hosts y los niveles de confianza de los archivos de enlace con los hosts y los niveles de confianza de la aplicación de la manera siguiente:  
  
-   **Puerto de envío.** El puerto de envío se enlaza a un controlador de envío del mismo nombre y a un host con el mismo nivel de confianza que los que están almacenados en el archivo de enlace.  
  
-   **Ubicación de recepción.** La ubicación de recepción se enlaza a un controlador de recepción del mismo nombre y a un host con el mismo nivel de confianza que los que están almacenados en el archivo de enlace.  
  
-   **Orquestaciones.** La orquestación se enlaza a un host del mismo nombre y con el mismo nivel de confianza que los que aparecen en el archivo de enlace.  
  
### <a name="order-in-which-bindings-are-applied"></a>Orden de aplicación de los enlaces  
 Cuando importa una aplicación, los enlaces se aplican en el orden siguiente:  
  
1.  Los enlaces de la aplicación generados por BizTalk Server que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
2.  Los enlaces de los archivos de enlace que se han agregado a la aplicación y que no tienen especificado un entorno de implementación de destino. Estos enlaces no se aplican en ningún orden específico.  
  
3.  Los enlaces de los archivos de enlace que se han agregado a la aplicación y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Estos enlaces no se aplican en ningún orden específico.  
  
 A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica.  
  
 Por ejemplo, si una aplicación que ya existe incluye un puerto de envío denominado SendPort1, y se aplica un archivo de enlace que describe un puerto de envío con el mismo nombre, la configuración del archivo de enlace sobrescribirá la configuración que ya existe para SendPort1. Si una aplicación que ya existe incluye una orquestación denominada, por ejemplo, ErrorHandling.ErrorHandler.ResubmitLogic, y un archivo de enlace describe una orquestación con el mismo nombre, todos los enlaces de la orquestación se escribirán con los enlaces del archivo de enlace.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)