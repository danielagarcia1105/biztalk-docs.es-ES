---
title: Importar esquemas de JD Edwards OneWorld en proyectos de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5954f92e55dac362387d66a8b65375e92fe187fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966149"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a>Importación de esquemas de JD Edwards OneWorld en proyectos de BizTalk Server
En este tema se trata la búsqueda de un servidor de JD Edwards OneWorld y la importación de los esquemas a un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Debe asegurarse de que establece el arglist. Debe actualizar jdearglist.txt antes de generar los esquemas en la orquestación. Para obtener más información, consulte [controlar los valores de cadena](../core/handling-string-values1.md).  
  
> [!NOTE]
>  Cada vez que cambie el jdearglist, debe regenerar los esquemas para ese objeto de negocios.  
  
 Después de crear el sistema lógico de JD Edwards OneWorld, puede explorar JD Edwards OneWorld abriendo el Asistente para adaptador de Microsoft desde un proyecto de BizTalk Server.  
  
### <a name="to-import-schemas"></a>Para importar esquemas  
  
1. Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2. Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] , seleccione **agregar**y seleccione **agregar elementos generados**.  
  
3. Haga clic en **agregar adaptador**y seleccione **abierto**.  
  
4. Seleccione el adaptador y haga clic en **siguiente**.  
  
    El JD. Sistema de Edwards OneWorld XE aparece en el explorador.  
  
    ![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")  
  
    El Asistente para adaptadores muestra un árbol con todos los sistemas definidos. JD Edwards OneWorld tiene demasiados módulos para mostrar en una lista larga. Los módulos se agrupan juntos de acuerdo con los tres primeros caracteres de su nombre.  
  
   - El primer nivel de la jerarquía es la lista de todos los prefijos de tres caracteres para los nombres de los módulos.  
  
   - El segundo nivel enumera todos los módulos que comparten el mismo prefijo de tres caracteres.  
  
   - El último nivel enumera las funciones empresariales que pertenecen a un módulo. Al expandir el icono servicios puede ver sus operaciones.  
  
     Al expandir una operación se muestran los argumentos de entrada y salida.  
  
     Puede expandir los argumentos de entrada y salida para ver los tipos de datos de los argumentos.  
  
   > [!NOTE]
   >  Si cambian las definiciones del objeto de servidor, deberá volver a generar el esquema para actualizar los datos que contiene.  
  
   > [!NOTE]
   >  Si cambia el archivo jdearglist.txt después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene. Para obtener información sobre jdearglist.txt, consulte [controlar los valores de cadena](../core/handling-string-values1.md).  
  
## <a name="generating-schemas"></a>Generación de esquemas  
 Use el siguiente procedimiento para generar esquemas.  
  
#### <a name="to-generate-schemas"></a>Procedimiento para generar esquemas  
  
1.  Seleccione el elemento para el cual desea importar esquemas.  
  
2.  Haga clic en (o arrastre) para agregar el elemento a la **transmisión** panel (para un entrante a J. Edwards OneWorld llamar).  
  
3.  Haga clic en **Aceptar**.  
  
     Los esquemas generados para el elemento seleccionado de JD Edwards OneWorld se importan en el proyecto de BizTalk Server.  
  
> [!NOTE]
>  Cuando se usa la libreta de direcciones (N0100041) es el nombre del campo **cActionCode**. La acción forma parte del propio archivo XML. Los códigos son:  
>   
>  --A para Agregar  
>   
>  --C para Cambiar  
>   
>  --D para Eliminar  
>   
>  --I para Consulta  
  
## <a name="see-also"></a>Vea también  
 [Agregar los artefactos a Administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)