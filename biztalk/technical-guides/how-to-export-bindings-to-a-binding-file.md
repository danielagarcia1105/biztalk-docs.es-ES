---
title: Cómo exportar enlaces a un archivo de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ab9dd60b37c16169f76e052706adb43c4606fcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982221"
---
# <a name="how-to-export-bindings-to-a-binding-file"></a>Cómo exportar enlaces a un archivo de enlace
Puede exportar los enlaces de una aplicación de BizTalk en otra aplicación de BizTalk existente utilizando un archivo de enlace. También puede exportar todos los enlaces en un grupo o el enlace de un ensamblado. Posteriormente, puede importar estos enlaces a una aplicación o un grupo.  
  
 Un archivo de enlace es un archivo XML que describe los artefactos de la base de datos de administración de BizTalk y sus relaciones. Contiene información de enlace para cada orquestación de BizTalk Server, canalización, asignación o esquema en el ámbito de un ensamblado, aplicación o el grupo de BizTalk. Contiene los valores de configuración para cada puerto de envío, grupo de puertos de envío, puerto de recepción, ubicación de recepción y la entidad. También se describe qué host depende de cada orquestación y su nivel de confianza.  
  
## <a name="why-to-export-to-a-binding-file"></a>Por qué se debe exportar a un archivo de enlace  
 Archivos de enlace pueden acelerar la implementación en los siguientes escenarios, ya que evita la necesidad de configurar manualmente los enlaces:  
  
- **Mover una aplicación desde un entorno de implementación a otro**  
  
   Mediante un archivo de enlace puede acelerar la implementación, ya que evita la necesidad de configurar manualmente los enlaces para diferentes entornos de implementación, como desde un entorno de desarrollo a un entorno de prueba.  
  
- **Actualización de un ensamblado**  
  
   Puede usar un archivo de enlace para aplicar automáticamente o volver a aplicar los enlaces a un ensamblado después de una actualización del ensamblado.  
  
- **Implementar un ensamblado en varios grupos de BizTalk**  
  
   Puede evitar la necesidad de configurar por separado los enlaces de ensamblado se implementa en varios grupos de BizTalk mediante el uso de un archivo de enlace.  
  
  Mediante un archivo de enlace proporciona flexibilidad para aplicar los enlaces a una aplicación. Al exportar una aplicación a un archivo .msi, solo se puede especificar que todos los enlaces de la aplicación se exportarán al archivo .msi. Con archivos de enlace puede hacer lo siguiente:  
  
- Exportar a un archivo de enlace sólo los enlaces para un único ensamblado, todos los enlaces del grupo actual o todos los enlaces de la aplicación actual. (Hacerlo mediante el comando Exportar enlaces para una aplicación en la consola de administración.)  
  
- Puede agregar un archivo de enlace a una aplicación (mediante el comando Agregar recursos) de forma que sus enlaces se aplican inmediatamente o bien los enlaces se aplican cuando la aplicación se importa en otro grupo.  
  
- Puede agregar varios archivos de enlace a una aplicación (mediante el comando Agregar recursos) y especificar un entorno de implementación de destino para cada uno de ellos. Esto le permite usar un paquete de implementación único para varios entornos de implementación. Al importar la aplicación, puede seleccionar qué enlaces va a aplicar.  
  
- Puede exportar los archivos de enlace independientes para varios ensamblados en una aplicación.  
  
- Después de generar los archivos de enlace, puede editarlos para cambiar su información de enlace.  
  
## <a name="how-to-export-to-a-binding-file"></a>Cómo exportar a un archivo de enlace  
 Exportar los enlaces de una aplicación en un archivo de enlace ejecutando el comando Exportar enlaces para la aplicación en la consola de administración de BizTalk Server, o mediante el comando BTSTask ExportBindings en la línea de comandos.  
  
 Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción.  
  
 La información de un archivo de enlace sustituye la información de configuración existente. Si el nombre de un artefacto en un archivo de enlace coincide con el nombre de un artefacto en la configuración existente, el artefacto del archivo de enlace actualizará el artefacto de la configuración existente al importar el archivo de enlace.  
  
 Para obtener información acerca de cómo los hosts y los niveles de confianza se almacenan en archivos de enlace, cómo se comparan los host y niveles de confianza en un archivo de enlace a hosts y confianza niveles en la aplicación y el orden en que se aplican los enlaces, vea [archivos de enlace y Implementación de aplicaciones](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726). Para obtener instrucciones sobre cómo exportar enlaces para una aplicación de BizTalk, consulte [cómo exportar enlaces para una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=155009) (http://go.microsoft.com/fwlink/?LinkId=155009).