---
title: "Validación en tiempo de ejecución para el motor de orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53adb5aa42c7dfe23df50707754bde200ea838a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="runtime-validation-for-the-orchestration-engine"></a>Validación en tiempo de ejecución del motor de orquestaciones
Puede configurar el motor de orquestaciones para realizar distintas validaciones en tiempo de ejecución que le ayuden a probar su orquestación y a diagnosticar los errores de datos o de configuración que se puedan producir.  
  
 Puede establecer marcas en BTSNTSvc.exe.config, un archivo de configuración que puede crear o editar en el mismo directorio que BTSNTSvc.exe (normalmente en el directorio de implementación de BizTalk). Puede establecer las marcas siguientes en el archivo BTSNTSvc.exe.config:  
  
-   Si establece la **ValidateAssemblies** indicador en `True`, el motor intenta cargar todos los ensamblados que se hace referencia a ensamblados dependientes inmediatos de una orquestación y en el error produce Microsoft.XLANGs.Core.AssemblyValidationException.  
  
-   Si establece la **ValidateSchemas** indicador en `True`, el motor utiliza System.Xml.XmlValidatingReader para validar cada esquema que representa un tipo de parte de mensaje y en caso de error, inicia System.Xml.XmlException.  
  
-   Si establece la **ValidateCorrelations** indicador en `True`, el motor comprueba que en un convoy paralelo todos los mensajes que coinciden con uno de los convoyes recibe tienen los mismos valores de propiedad de correlación y en caso de error produce Microsoft.XLANGs.Core.CorrelationValidationException.  
  
-   Si establece la **ExtendedLogging** indicador en `True`, el motor muestra las propiedades promocionadas en la información para Microsoft.XLANGs.BaseTypes.PublishMessageException para el mensaje que no se pudo publicar.  
  
 Si desea deshabilitar una validación, quite la marca completamente del archivo de configuración. Cuando todas las validaciones estén activadas, el motor validará los ensamblados, los esquemas y las correlaciones. Para obtener más información y ejemplos del archivo BTSNTSvc.exe.config, consulte [configuración del motor de orquestación](../core/orchestration-engine-configuration.md).  
  
## <a name="validate-assemblies"></a>Validar ensamblados  
 El motor de orquestaciones comprueba que están disponibles los ensamblados a los que hace referencia la orquestación Para que la validación se realice correctamente, todos los ensamblados a los que se hace referencia deben estar en la Caché de ensamblados global (GAC) cuando se activa la primera instancia de la orquestación. Si se produce un error en la validación, se registrará un error en el registro de la aplicación y se suspenderá la orquestación.  
  
## <a name="validate-schemas"></a>Validar esquemas  
 Cada vez que se asigna una parte XSD, el motor de orquestaciones validará los datos de la parte con su esquema. Si se produce un error en la validación, se registrará el error en el registro de la aplicación y se producirá una excepción.  
  
## <a name="validate-correlation"></a>Validar correlaciones  
 El motor de orquestaciones confirmará que se reflejan los valores de la propiedad especificados para la correlación con una instancia específica de una orquestación en cualquier mensaje que se envíe desde dicha instancia de la orquestación. Si **validateCorrelation** no se establece, el motor supondrá que el mensaje enviado contiene los valores de correlación correctos y no se realizará ninguna comprobación.  
  
 Si se produce un error en ninguna validación de correlación, el motor se registrará un error en el registro de aplicación y producirá una excepción de tipo **CorrelationValidationException**.  
  
 De forma predeterminada, **validateCorrelation** no se ha establecido.  
  
## <a name="see-also"></a>Vea también  
 [Depurar orquestaciones](../core/debugging-orchestrations.md)   
 [Configuración del motor de orquestación](../core/orchestration-engine-configuration.md)