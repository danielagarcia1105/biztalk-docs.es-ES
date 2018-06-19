---
title: Importar esquemas de PeopleSoft en Visual Studio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6af82459f8b51f3dfa73a52593db18d25365c2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013539"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a>Importar esquemas de PeopleSoft en proyectos de BizTalk Server
Cuando haya creado el sistema PeopleSoft Enterprise, puede examinar el servidor e importar esquemas en un proyecto BizTalk Server.  
  
## <a name="browse-a-peoplesoft-server-system"></a>Examinar un sistema de servidor de PeopleSoft  
  
1.  Haga clic con el botón secundario en un proyecto de BizTalk Server y seleccione una de las siguientes opciones.  
  
    -   Si ya tiene un esquema generado para el objeto, seleccione **agregar**, haga clic en **Agregar esquema** y, a continuación, seleccione el esquema existente para agregar a la orquestación.  
  
    -   Si no tiene un esquema generado para el objeto, seleccione **agregar**, a continuación, haga clic en **agregar elementos generados**y, a continuación, seleccione el adaptador. Este es el mismo nombre que escribió en el **AdapterProperties** cuadro de diálogo. Para obtener más información, consulte "Cuadro de diálogo Propiedades de adaptador" en la Ayuda principal de BizTalk.  
  
2.  Haga clic en Siguiente.  
  
     El sistema PeopleSoft Enterprise aparece en el explorador.  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>Interfaces de componentes  
 En el **Interfaces de componentes** carpeta (CI), puede ver todas las interfaces de componentes disponibles en el sistema. Una interfaz de componente declara el conjunto de métodos y propiedades que admite. Una interfaz de componente no implementa el comportamiento o las propiedades. El adaptador de Microsoft BizTalk para PeopleSoft Enterprise expone métodos estándar, como CreateEx, DeleteOnly, Find, Get y UpdateEx. Para obtener una descripción de estos métodos, consulte [métodos de interfaz de componente de apéndice A:](../core/appendix-a-component-interface-methods.md).  
  
## <a name="generate-schemas"></a>Generar esquemas  
  
Seleccione el elemento para el que desea importar esquemas: un **mensaje**, **consulta**, o **interfaz de componente**.  BizTalk Server genera los esquemas para el elemento seleccionado y los importa en un proyecto de BizTalk Server.  
  
> [!NOTE]
>  Si cambia las definiciones de objeto de servidor, debe volver a generar el esquema para actualizar los datos que contiene.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de PeopleSoft](../core/creating-peoplesoft-send-handlers.md)