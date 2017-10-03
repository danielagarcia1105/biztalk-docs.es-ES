---
title: BtarnConfig | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9221e530266091795260bc7d4fd7e8788e066335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btarnconfig"></a>BtarnConfig
Use la utilidad BtarnConfig para importar datos de configuración en, o exportar datos de configuración de, un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] entorno. Estos datos de configuración son los datos que se establece mediante la consola de administración de BTARN, incluidos los valores de configuración de proceso, organizaciones internas, socios comerciales y acuerdos.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*> \ archivos de programa\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK  
  
## <a name="running-btarnconfig"></a>Ejecutando BtarnConfig  
  
#### <a name="to-run-btarnconfig"></a>Para ejecutar BtarnConfig  
  
1.  Abra un símbolo del sistema.  
  
2.  Mover a \< *unidad*> \ archivos de programa\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\\.  
  
3.  En el símbolo del sistema, escriba **BtarnConfig**, escriba los modificadores correspondientes y, a continuación, presione ENTRAR.  
  
    > [!NOTE]
    >  En la siguiente sección se describe los modificadores.  
  
## <a name="syntax-for-btarnconfig"></a>Sintaxis de BtarnConfig  
 A continuación se muestra la sintaxis que se utiliza para iniciar esta herramienta de línea de comandos:  
  
### <a name="syntax-for-importing-configuration-data"></a>Sintaxis para importar datos de configuración  
  
```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-for-exporting-configuration-data"></a>Sintaxis para exportar datos de configuración  
  
```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-description"></a>Descripción de la sintaxis  
 En la tabla siguiente describe cada parte de la sintaxis que usa la utilidad BtarnConfig.  
  
|Sintaxis|Description|  
|------------|-----------------|  
|\<*nombre de archivo*.xml >|Ruta de acceso completa del archivo para importar o exportar desde. Si no se proporciona una ruta de acceso, en BTARN se da por supuesto que la ruta de acceso es \< *unidad*> \ archivos de programa\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK.|  
|**E IMPORTACIÓN**|Importa los datos XML de \< *filename*.xml > en la configuración de BTARN.|  
|**/ EXPORTACIÓN**|Exporta la configuración de BTARN como datos XML a \< *filename*.xml >.|  
|**/H**|Importa o exporta los datos de configuración de la organización principal.|  
|**/P**|Importa o exporta datos de configuración de socios comerciales.|  
|**/R**|Importa o exporta datos de configuración de proceso.|  
|**/A**|Importa o exporta datos de configuración del acuerdo.|  
  
## <a name="remarks"></a>Comentarios  
 Si no se proporciona uno de los **/H**, **/P**, **/r**, o **/A** se activa, el BtarnConfig utilidad importa o exporta todos los datos. Al exportar todos los datos en una sola operación, BtarnConfig exporta los datos en el archivo XML en el orden siguiente: inicio de las organizaciones, socios comerciales, la configuración del proceso y acuerdos.  
  
 Si hay un problema con el archivo que va a importar desde estructural, BTARN detectará el error durante la fase de validación de esquema y se producirá un error en la operación antes de importan los datos. Si se produce otro error, por ejemplo, está intentando importar un artefacto duplicado o HTTPS es necesario para el contrato de PIP y, a continuación, se producirá un error en la operación de importación. Sin embargo, todos los datos se importarán hasta que punto permanecerá en la configuración.  
  
 Debe ser un administrador de BizTalk para importar o exportar datos de configuración con BtarnConfig. Si no es un administrador de BizTalk, algunas operaciones de importación pueden producir un error debido a problemas de acceso. Sin embargo, otras operaciones de importación en el mismo comando BtarnConfig pueden realizarse correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)