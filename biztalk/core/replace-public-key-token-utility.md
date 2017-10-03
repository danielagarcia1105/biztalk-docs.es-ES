---
title: "Reemplace la utilidad de símbolo (token) de clave pública | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dee6fff7de065c3663ab373f739f7fb465947c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="replace-public-key-token-utility"></a>Utilidad para reemplazar el token de clave pública
Esta utilidad se puede usar para reemplazar un token de clave pública o una variable de un archivo por un token de clave pública derivado de un archivo de clave de ensamblado de nombre seguro (.snk).  
  
 Esta utilidad puede resultar útil cuando un programador escribe un script que usa el [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md) para implementar un ensamblado. Para que la implementación se realice correctamente, se debe proporcionar el nombre completo del ensamblado, que incluye el token de clave pública correspondiente. El token de clave pública de un ensamblado se extrae de un archivo .snk y se asigna al ensamblado cuando se crea. Sin embargo, antes de que el ensamblado se implemente en un nuevo entorno, a menudo se vuelve a generar (compilar) con un token de clave pública diferente. Como resultado, es posible que el programador desconozca el token de clave pública que se usará para el ensamblado cuando se ejecute la secuencia de comandos de implementación.  
  
 La utilidad para reemplazar el token de clave pública se puede usar de dos formas en esta situación:  
  
-   **Escenario 1.** En la secuencia de comandos de implementación, el programador puede usar un token de clave pública o un marcador de posición que represente al token de clave pública. Antes de ejecutar la secuencia de comandos, un usuario puede ejecutar la utilidad para reemplazar el token de clave pública para sustituir el token de clave pública o el marcador de posición del archivo de secuencia de comandos por el token de clave pública extraído del archivo .snk que se usó para crear el ensamblado para el entorno de destino.  
  
-   **Escenario 2.** El programador puede configurar la secuencia de comandos para sustituir automáticamente el nuevo token de clave pública, como sigue: al principio de la secuencia de comandos, invoque la utilidad de Token de clave pública y haga que señale a un archivo .snk que contiene el token de clave pública. Dentro de la secuencia de comandos, use la variable de entorno %NEWTOKEN% para representar el token de clave pública. Cuando se ejecute la secuencia de comandos, la utilidad extraerá el valor del token de clave pública del archivo .snk y lo establecerá en una variable de entorno %NEWTOKEN%. Al ejecutar la secuencia de comandos, cada instancia de %NEWTOKEN% se sustituirá con el token de clave pública del archivo .snk especificado. Por ejemplo:  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 La utilidad para reemplazar el token de clave pública se encuentra en:  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\ReplacePublicKeyToken\\.  
  
 La utilidad para reemplazar el token de clave pública consta de tres archivos:  
  
-   ReplacePKT.bat  
  
-   ReplacePKT.vbs  
  
-   ReplacePKT.wsf  
  
## <a name="procedures"></a>Procedimientos  
 Siga el procedimiento siguiente para reemplazar todas las instancias de un token de clave pública o un marcador de posición de un archivo con el token de clave pública extraído de un archivo .snk, tal como se describe en el escenario 1.  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a>Para reemplazar instancias de un token de clave pública o un marcador de posición de un archivo  
  
1.  Asegúrese de que los tres archivos de la utilidad para reemplazar el token de clave pública (ReplacePKT.bat, ReplacePKT.vbs y ReplacePKT.wsf), el archivo de secuencia de comandos y el archivo .snk están disponibles en el equipo local.  
  
2.  En una ventana de comandos, cambie el directorio a la carpeta que contiene los archivos de la utilidad para reemplazar el token de clave pública.  
  
3.  Desde el símbolo del sistema, ejecute el siguiente comando:  
  
4.  **ReplacePKT \<**  *archivo .snk*  **>  \<**  *anterior token de clave pública*  **>  \<**  *archivo para que reemplace***>**  
  
    |Opción|Description|  
    |------------|-----------------|  
    |**\<***archivo .snk***>**|Ruta de acceso completa del archivo .snk que contiene el token de clave pública que desea sustituir por el token de clave pública o marcador de posición existente.|  
    |**\<***anterior token de clave pública***>**|Token de clave pública o marcador de posición que desea reemplazar.|  
    |**\<***archivo para que reemplace***>**|Ruta de acceso completa del archivo en el que desea reemplazar el token de clave pública o marcador de posición.|  
  
     Ejemplo:  
  
     **ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**  
  
 Siga el procedimiento siguiente para establecer automáticamente una variable de entorno en una secuencia de comandos que use un token de clave pública derivado de un archivo .snk, tal como se describe en el escenario 2.  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a>Para establecer una variable de entorno que use un token de clave pública  
  
1.  Agregue la siguiente línea de código al principio del archivo de comandos:  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     Donde \< *filename*> es el nombre del archivo .snk del que se deriva el token de clave pública.  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  En el archivo de script, utilice `%NEWTOKEN%` para representar el token de clave pública.  
  
     Ejemplo:  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  Cuando entregue el archivo de secuencia de comandos a los usuarios, incluya los tres archivos de la utilidad para reemplazar el token de clave pública (ReplacePKT.bat, ReplacePKT.vbs y ReplacePKT.wsf). Asegúrese de que los usuarios de la secuencia de comandos, copian todos los archivos en la misma carpeta del sistema de archivos antes de ejecutarla.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades del SDK de](../core/utilities-in-the-sdk.md)