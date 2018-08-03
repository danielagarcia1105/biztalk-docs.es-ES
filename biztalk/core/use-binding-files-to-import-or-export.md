---
title: Usar archivos de enlace para importar o exportar | Microsoft Docs
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
ms.openlocfilehash: b9ed0f50d6a6d841169b16f3f3ffd485ee345aeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990597"
---
# <a name="use-binding-files-to-import-or-export"></a>Usar archivos de enlace para importar o exportar

A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede exportar e importar archivos de enlace en el **partes** y **acuerdo** niveles. Para versiones anteriores de BizTalk, exportar en el nivel de aplicación, como se describe en: 

* [Cómo exportar enlaces para una solución EDI y AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Cómo importar enlaces para una solución EDI y AS2](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

En este tema se muestra cómo importar y exporta las partes, sus perfiles, contratos, configuración de reserva y utilizando más [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] y BTSTask. 

## <a name="overview"></a>Información general

Algunas de las características de importación y exportación incluyen:

* Importar entidades, perfiles de negocio y contratos desde un archivo de enlace XML
* Exportar entidades, perfiles de negocio, acuerdos y configuración de reserva de EDI en un archivo de enlace XML
* Al importar un archivo de enlace, puede decidir no importar las partes, o la configuración de reserva
* Cuando se importan en el nivel de entidades, se importan solo las entidades y contratos en el archivo de enlace
* Exportar entidades específicas en el mismo archivo de enlace y optar por exportar también todos los contratos asociados con dichos terceros
* El Asistente Importar aplicación de enlace le permite elegir importar la configuración de seguimiento o excluir las entidades.
* BTSTask incluye la `ImportParties` y `ExportParties` comandos 

## <a name="prerequisites"></a>Requisitos previos

* Debe haber iniciado sesión con una cuenta que sea miembro de la ** grupo de administradores de servidor BizTalk **. Consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  

* Debe haber agregado una referencia a la **aplicación EDI de BizTalk** desde una aplicación de BizTalk que se usará como una aplicación de EDI. Consulte [pasos posteriores a la configuración](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).

## <a name="import-or-export-all-the-trading-partners"></a>Importar o exportar a todos los socios comerciales
1. Abra **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** y expanda el grupo de BizTalk.
2. Haga clic en **partes**y seleccione **exportar**. 

    Cuando se exportan en el **partes**-nivel, que va a exportar todos los socios comerciales. Esto también exporta todos los elementos utilizados por los socios comerciales, incluidos perfiles de negocio y los contratos en un archivo XML. 

3. Haga clic en **partes**, seleccione **importación**y seleccione el archivo XML de enlace. 

      Elegir **excluir partes**, o **excluir la configuración de reserva de EDI** por lo que no se importan. En caso contrario, todo el contenido del archivo de enlace se importa, incluidos los socios, perfiles de negocio y acuerdos comerciales.     

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

Consulte [ImportParties (comando)](../core/importparties-command.md).

    
## <a name="export-individual-partners"></a>Exportar individuales asociados
1. En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, seleccione **partes**.
2. En el **entidades y perfiles empresariales** panel, haga clic en una entidad y seleccione **exportar**.

    Al exportar una entidad específica, tiene la opción para exportar todas las entidades y todos los acuerdos utilizados por esa entidad. Puede desactivar **exportar entidades seleccionadas y todos los acuerdos dentro de las partes seleccionadas** para exportar sólo la entidad que seleccione.

3. Seleccione **Aceptar**. 

> [!TIP]
> En el **entidades y perfiles empresariales** panel, también puede usar el **CTRL** y **MAYÚS** teclas para seleccionar varias entidades en la lista. Todas las entidades que seleccione exportación en el mismo archivo de enlace.

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

Consulte [ExportParties (comando)](../core/exportparties-command.md).


## <a name="import-application-binding-file"></a>Importar archivo de enlace de aplicaciones

En el nivel de aplicación, puede importar un archivo de enlace con entidades de EDI y AS2. 

1. En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expanda **aplicaciones**
2. Haga clic en la aplicación y seleccione **importación**.
3. **Importar la configuración de seguimiento** y **excluir partes** opciones están disponibles. Con estas opciones, puede elegir importar ninguna configuración de seguimiento existente o excluir todas las entidades EDI y AS2 en el archivo de enlace.

    | Configuración | Detalles |
    |---|---|
    |**Importar la configuración del seguimiento** | Importa la configuración de seguimiento habilitada en los diferentes artefactos dentro de la aplicación, como el seguimiento de partes de mensaje y seguimiento de eventos. <br/><br/>Habilitado de forma predeterminada para garantizar la compatibilidad con versiones anteriores. |
    | **Excluir entidades**|Hace no importar entidades, perfiles y los acuerdos que existan dentro del archivo. <br/><br/>Deshabilitada de forma predeterminada para garantizar la compatibilidad con versiones anteriores.|

   > [!IMPORTANT]
   > Invalida la configuración de seguimiento global **importar la configuración de seguimiento**. Por lo que si ha deshabilitado el seguimiento a nivel global de nivel, cualquier configuración no se importa de seguimiento, incluso si **importar la configuración de seguimiento** está activada.
   > 
   > **Panel de configuración de BizTalk, página grupo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explica la **Permitir importar configuración seguimiento** configuración global.

### <a name="btstask-example"></a>Ejemplo de BTSTask

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

Consulte [ImportBindings (comando)](../core/importbindings-command.md).

## <a name="in-this-section"></a>En esta sección
Para importar o exportar los archivos de enlace de EDI y AS2 en versiones anteriores de BizTalk, consulte: 

* [Cómo exportar enlaces para una solución EDI y AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Cómo importar enlaces para una solución EDI y AS2](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
