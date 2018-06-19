---
title: Usar archivos de enlace para importar o exportar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22288276"
---
# <a name="use-binding-files-to-import-or-export"></a>Usar archivos de enlace para importar o exportar

A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede exportar e importar archivos de enlace en el **partes** y **acuerdo** niveles. Para las versiones anteriores de BizTalk, exportar en el nivel de aplicación, como se describe en: 

* [Cómo exportar enlaces para una solución EDI y AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Cómo importar enlaces para una solución EDI y AS2](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

En este tema muestra cómo importar y exporta entidades, sus perfiles, acuerdos, configuración de reserva y usar más [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] y BTSTask. 

## <a name="overview"></a>Información general

Algunas de las características de importación y exportación son:

* Importar entidades y perfiles de negocio, acuerdos desde un archivo de enlace XML
* Exportar entidades, perfiles de negocio, acuerdos y configuración de reserva de EDI en un archivo de enlace XML
* Al importar un archivo de enlace, puede decidir no importar las entidades o la configuración de reserva
* Cuando se importan en el nivel de entidades, solo las entidades y acuerdos en el archivo de enlace se importan
* Exportar entidades específicas en el mismo archivo de enlace y optar por exportar todos los acuerdos asociados con esas entidades
* El Asistente para enlace de importación de aplicaciones le permite elegir importar la configuración de seguimiento o excluir las entidades.
* BTSTask incluye la `ImportParties` y `ExportParties` comandos 

## <a name="prerequisites"></a>Requisitos previos

* Debe haber iniciado sesión con una cuenta que sea miembro de la ** grupo de administradores de servidor BizTalk **. Vea [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  

* Debe haber agregado una referencia a la **aplicación EDI de BizTalk** desde una aplicación de BizTalk que se usará como una aplicación de EDI. Vea [pasos posteriores a la configuración](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).

## <a name="import-or-export-all-the-trading-partners"></a>Importar o exportar a todos los socios comerciales
1. Abra **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** y expanda el grupo de BizTalk.
2. Haga clic en **partes**y seleccione **exportar**. 

    Cuando se exportan en el **partes**-nivel, que va a exportar todos los socios comerciales. También exporta todos los elementos utilizados por los socios comerciales, incluidos los perfiles de negocio y los contratos en un archivo XML. 

3. Haga clic en **partes**, seleccione **importación**y seleccione el archivo de enlace XML. 

      Elegir **excluir entidades**, o **excluir la configuración de reserva de EDI** por lo que no se importan. En caso contrario, todo el contenido del archivo de enlace se importa, incluidos el comercial socios, perfiles de negocio y acuerdos.     

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

Vea [ImportParties comando](../core/importparties-command.md).

    
## <a name="export-individual-partners"></a>Asociados de negocios individuales de exportación
1. En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, seleccione **partes**.
2. En el **entidades y perfiles empresariales** panel, haga clic en una entidad y seleccione **exportar**.

    Cuando se exporta una entidad específica, se tiene la opción para exportar todas las entidades y todos los acuerdos utilizados por esa entidad. Puede desactivar **exportar entidades seleccionados y todos los acuerdos dentro de las entidades seleccionadas** para exportar solo la entidad que seleccione.

3. Seleccione **Aceptar**. 

> [!TIP]
> En el **entidades y perfiles empresariales** panel, también puede usar el **CTRL** y **MAYÚS** teclas para seleccionar varias entidades en la lista. Todas las entidades que seleccione exportación al mismo archivo de enlace.

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

Vea [ExportParties comando](../core/exportparties-command.md).


## <a name="import-application-binding-file"></a>Importar archivo de enlace de aplicaciones

En el nivel de aplicación, puede importar un archivo de enlace con entidades EDI y AS2. 

1. En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expanda **aplicaciones**
2. Haga clic en la aplicación y seleccione **importación**.
3. **Importar la configuración de seguimiento** y **excluir entidades** opciones están disponibles. Usar estas opciones, puede importar cualquier configuración de seguimiento existente o excluir todas las entidades EDI/AS2 en el archivo de enlace.

    | Configuración | Detalles |
    |---|---|
    |**Importar la configuración del seguimiento** | Importa la configuración de seguimiento habilitada en los diferentes artefactos dentro de la aplicación, como el seguimiento de partes de mensaje y seguimiento de eventos. <br/><br/>Habilitado de forma predeterminada para garantizar la compatibilidad con versiones anteriores. |
    | **Excluir entidades**|Hace no importar entidades, perfiles y acuerdos que existan dentro del archivo. <br/><br/>Deshabilitada de forma predeterminada para garantizar la compatibilidad con versiones anteriores.|

     > [!IMPORTANT] 
     > Invalida la configuración de seguimiento global **importar la configuración de seguimiento**. Por lo que si ha deshabilitado el seguimiento a nivel global de nivel, cualquier configuración no se importa de seguimiento, aunque **importar la configuración de seguimiento** está activada.
     > 
     > **Panel de configuración de BizTalk, página grupo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explica el **permitir la importación de la configuración del seguimiento** configuración global.

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

Vea [comando ImportBindings](../core/importbindings-command.md).

## <a name="in-this-section"></a>En esta sección
Para importar o exportar los archivos de enlace de EDI y AS2 en versiones anteriores de BizTalk, vea: 

* [Cómo exportar enlaces para una solución EDI y AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Cómo importar enlaces para una solución EDI y AS2](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
