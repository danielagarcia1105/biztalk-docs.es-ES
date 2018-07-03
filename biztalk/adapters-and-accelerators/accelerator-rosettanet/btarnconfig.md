---
title: BtarnConfig | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542ed5729ce4f5ed7ca4a6d453b3169bb1f43d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991469"
---
# <a name="btarnconfig"></a>BtarnConfig
Use la utilidad BtarnConfig para importar datos de configuración en, o exportar datos de configuración desde un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] entorno. Estos datos de configuración son los datos que se establece mediante la consola de administración de BTARN, incluida la configuración del proceso, organizaciones principales, socios y acuerdos.  

## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK  

## <a name="running-btarnconfig"></a>Ejecutando BtarnConfig  

#### <a name="to-run-btarnconfig"></a>Para ejecutar BtarnConfig  

1. Abra un símbolo del sistema.  

2. Mover a \< *unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  

3. En el símbolo del sistema, escriba **BtarnConfig**, escriba los modificadores adecuados y, a continuación, presione ENTRAR.  

   > [!NOTE]
   >  La siguiente sección describe los modificadores.  

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


|       Sintaxis       |                                                                                                                          Descripción                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<*nombre de archivo*.xml\> | Ruta de acceso completa del archivo para importar o exportar desde. Si no se proporciona una ruta de acceso, BTARN supone que la ruta de acceso es \< *unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> aceleración de menú SDK DE. |
|    **E IMPORTACIÓN**     |                                                                                          Importa los datos XML de \< *filename*.xml\> en la configuración de BTARN.                                                                                           |
|    **/ EXPORT**     |                                                                                             Exporta la configuración de BTARN como datos XML a \< *filename*.xml\>.                                                                                              |
|       **/H**       |                                                                                                   Importa o exporta datos de configuración de la organización.                                                                                                    |
|       **/P**       |                                                                                                        Importa o exporta datos de configuración asociado.                                                                                                         |
|       **/R**       |                                                                                                        Importa o exporta datos de configuración de proceso.                                                                                                         |
|       **/A**       |                                                                                                       Importa o exporta datos de configuración del acuerdo.                                                                                                        |

## <a name="remarks"></a>Notas  
 Si no se proporciona uno de los **/H**, **/P**, **/R**, o **/A** cambia, el BtarnConfig utilidad importa o exporta todos los datos. Al exportar todos los datos en una sola operación, BtarnConfig exporta los datos en el archivo XML en el orden siguiente: las organizaciones, la configuración del proceso, socios y acuerdos de inicio.  

 Si hay un problema con el archivo que se va a importar desde estructural, BTARN detectará el error durante la fase de validación de esquema y se producirá un error en la operación antes de importaron los datos. Si se produce otro error, por ejemplo, está intentando importar un artefacto duplicado o HTTPS es necesario para el acuerdo de PIP, se producirá un error en la operación de importación. Sin embargo, todos los datos se importan hasta que punto permanecerá en la configuración.  

 Debe ser un administrador de BizTalk para importar o exportar datos de configuración utilizando BtarnConfig. Si no es un administrador de BizTalk, algunas operaciones de importación pueden producir un error debido a problemas de acceso. Sin embargo, otras operaciones de importación en el mismo comando BtarnConfig pueden ser correcta.  

## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
