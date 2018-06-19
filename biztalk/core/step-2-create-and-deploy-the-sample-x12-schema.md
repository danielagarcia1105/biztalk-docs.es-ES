---
title: 'Paso 2: Crear e implementar el ejemplo X12 esquema | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57c95ac64637027b5d39699a42e8fac93c003697
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974474"
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a>Paso 2: Crear e implementar el ejemplo X12 esquema
![Paso 2 de 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")  
  
 En este paso, generará e implementará el proyecto que proporciona un esquema X12 de EDI de ejemplo necesario para procesar el intercambio entrante X12 de EDI que se transporta por medio de AS2. En este tutorial, el esquema es X12_00401_864.xsd. No necesita cambiar el proyecto que se envía con el tutorial de AS2, sólo debe generarlo.  
  
> [!NOTE]
>  El archivo de esquema X12_00401_864.xsd que este tutorial usa se almacena en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas. También se agrega al proyecto de esquemas que generará e implementará en este paso. Este esquema es diferente del archivo X12_00401_864.xsd descargado en el equipo mediante la ejecución de MicrosoftEdiXsdTemplates.exe en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI. Este tutorial sólo funcionará si utiliza el archivo X12_00401_864.xsd que se ha agregado a Schemas.btproj.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a>Para crear e implementar el esquema X12 de ejemplo  
  
1.  Iniciar **Microsoft Visual Studio** como administrador.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra la solución [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
3.  Haga clic en el proyecto de esquemas y, a continuación, haga clic en **propiedades**. Haga clic en el **firma** ficha en el Diseñador de proyectos. Compruebe el **firmar el ensamblado** casilla de verificación para **elegir un archivo de nombre de clave seguro**, seleccione  **\<nuevo... \>**  y escriba `Schemas.snk`. Desactive **proteger mi archivo de clave con una contraseña** y, a continuación, haga clic en **Aceptar**. Cierre el cuadro de diálogo de propiedades del proyecto y guarde los cambios.  
  
4.  Genere e implemente Schemas.btproj.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar un perfil de entidad y de negocio para su organización (Contoso), como se describe en [paso 3: configurar una entidad y perfil de negocio para su organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).  
  
## <a name="see-also"></a>Vea también  
 [Esquemas de documentos EDI](../core/edi-document-schemas.md)