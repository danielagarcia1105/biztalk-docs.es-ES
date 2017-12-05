---
title: AddResource (comando) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 875a087fa3afe7515aee2c406cbc47551bea1f4d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="addresource-command"></a>AddResource (comando)
Los temas de esta sección proporcionan información de referencia acerca de los parámetros del comando AddResource. Los parámetros que utilizan con este comando varían según el tipo de artefacto que se va a agregar. Para obtener una lista completa de tipos de artefactos, use la **ListTypes** de comandos, como se describe en [comando ListTypes](../core/listtypes-command.md).  
  
 Para obtener ayuda acerca de cómo agregar un tipo de artefacto determinado, escriba el comando siguiente:  
  
 **BTSTask AddResource/Type:**\<*nombre de tipo* \> **/?**  
  
> [!NOTE]
>  Si el artefacto que está agregando tiene un nombre de ruta de acceso muy largo, incluido el nombre de archivo, se producirá un error en la operación de agregar el artefacto a la aplicación. Una ruta de acceso no puede superar los 260 caracteres.  
>   
>  Si se produce un error en una operación de agregación, todas las acciones realizadas durante la operación se deshacen, con excepción de los ensamblados, que no se quitan de la caché de ensamblados global cuando han sido agregados por este comando, y las entradas, que no se quitan del Registro de Windows si no se ha creado ninguna entrada.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [AddResource (comando): ensamblado de BizTalk](../core/addresource-command-biztalk-assembly.md)  
  
-   [AddResource (comando): enlace de BizTalk](../core/addresource-command-biztalk-binding.md)  
  
-   [AddResource (comando): ensamblado de .NET](../core/addresource-command-net-assembly.md)  
  
-   [AddResource (comando): artefacto de BAM](../core/addresource-command-bam-artifact.md)  
  
-   [AddResource (comando): certificado](../core/addresource-command-certificate.md)  
  
-   [AddResource (comando): componente de COM](../core/addresource-command-com-component.md)  
  
-   [AddResource (comando): archivo](../core/addresource-command-file.md)  
  
-   [AddResource (comando): script de preprocesamiento](../core/addresource-command-preprocessing-script.md)  
  
-   [AddResource (comando): script de posprocesamiento](../core/addresource-command-postprocessing-script.md)  
  
-   [AddResource (comando): directiva](../core/addresource-command-policy.md)  
  
-   [AddResource (comando): directorio virtual](../core/addresource-command-virtual-directory.md)