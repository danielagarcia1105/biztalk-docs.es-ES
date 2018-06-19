---
title: Componentes de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a5f2a78a9ea555d22f585c0aa50eda65b6c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225332"
---
# <a name="adapter-components"></a>Componentes del adaptador
Los adaptadores personalizados comparten los mecanismos estándar de configuración, administración y configuración que los adaptadores nativos usan. Con la estandarización al marco de adaptador, un adaptador personalizado se administra mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 La siguiente ilustración muestra los componentes principales de un adaptador personalizado: el archivo de registro del adaptador, el componente de tiempo de diseño del adaptador y el componente de tiempo de ejecución del adaptador.  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a>Archivo de Registro del adaptador  
 Es necesario que determinada información acerca de los adaptadores se registre en el Registro y en la base de datos de administración de BizTalk. La información como es el alias del adaptador, el controlador de recepción, la ubicación de recepción y el tipo de transporte se denomina metadatos. Estos metadatos se crean durante el registro manual del adaptador mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. También, puede ejecutar la utilidad SDK del Asistente para el Registro del adaptador (AdapterRegistryWizard.exe) con el fin de generar un archivo de Registro para el adaptador personalizado. Haga doble clic en este archivo de registro o haga clic en **importación** en el **archivo** menú utilizando el editor del registro (regedit32.exe) escribe los metadatos en el registro.  
  
> [!NOTE]
>  La ejecución de este archivo de Registro no agrega información del adaptador a la base de datos de administración de BizTalk. Debe hacerlo manualmente mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="design-time-component"></a>Componente de tiempo de diseño  
 La interfaz de usuario (UI) de un adaptador personalizado se implementa mediante el marco de trabajo de adaptadores. Es un enfoque productivo al desarrollo de la interfaz de usuario porque ésta se representa a partir de un esquema XML proporcionado como parte del ensamblado del adaptador. Se necesita poco código para transformar el contenido del esquema en una interfaz de usuario para configurar las propiedades del adaptador.  
  
 En el caso de una orquestación que necesite comunicar con un adaptador de aplicación como el adaptador de SQL, el Asistente para agregar metadatos de adaptador permite agregar a un proyecto de BizTalk metadatos de adaptador, como por ejemplo esquemas, tipos de mensaje y tipos de puerto. Use este asistente con los adaptadores de aplicación para insertar los esquemas correspondientes en el sistema. Para invocar este asistente desde dentro de un proyecto de BizTalk (no adaptador), haga clic en el proyecto, seleccione **agregar elementos generados**, haga clic en **agregar metadatos de adaptador** y, a continuación, seleccione en la lista de registrados adaptadores para importar los metadatos de adaptador.  
  
## <a name="run-time-component"></a>Componente de tiempo de ejecución  
 Normalmente un adaptador consta de dos componentes de tiempo de ejecución públicos: el componente que implementa el receptor del mensaje y el componente que implementa el remitente del mensaje. Estos componentes se pueden implementar en el mismo ensamblado o en dos diferentes.  
  
#### <a name="receive-adapter"></a>Adaptador de recepción  
 El adaptador de recepción es el responsable de la creación de un mensaje nuevo de BizTalk al adjuntar la secuencia de origen de datos o red al cuerpo del mensaje. También agrega todos los metadatos adecuados al extremo en el que se recibieron los datos y, después, envía el mensaje al motor de mensajería. El adaptador elimina los datos del extremo de recepción o envía el mensaje de confirmación correspondiente al cliente que indica que se ha aceptado los datos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="send-adapter"></a>Adaptador de envío  
 El adaptador de envío es el responsable del envío de un mensaje de BizTalk al extremo especificado mediante su protocolo de transporte específico.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el marco de trabajo?](../core/what-is-the-adapter-framework.md)