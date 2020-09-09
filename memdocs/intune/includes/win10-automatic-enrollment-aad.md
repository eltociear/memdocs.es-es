## <a name="enable-windows-10-automatic-enrollment"></a>Habilitar la inscripción automática de Windows 10

La inscripción automática permite a los usuarios inscribir sus dispositivos Windows 10 en Intune. Para inscribirse, los usuarios deben agregar su cuenta profesional a los dispositivos personales o conectar dispositivos corporativos a Azure Active Directory. En segundo plano, el dispositivo se registra y se une a Azure Active Directory. Una vez se registra un dispositivo, este se administra con Intune.

**Requisitos previos**

- Suscripción a Azure Active Directory Premium ([suscripción de prueba](https://go.microsoft.com/fwlink/?LinkID=816845))
- Suscripción a Microsoft Intune

### <a name="configure-automatic-mdm-enrollment"></a>Configurar la inscripción de MDM automática

1. Inicie sesión en [Azure Portal](https://portal.azure.com) y seleccione **Azure Active Directory**.

   ![Captura de pantalla de Azure Portal](../enrollment/media/windows-enroll/auto-enroll-azure-main.png)

2. Seleccione **Movilidad (MDM y MAM)** .

   ![Captura de pantalla de Azure Portal](../enrollment/media/windows-enroll/auto-enroll-mdm.png)

3. Seleccione **Microsoft Intune**.

   ![Captura de pantalla de Azure Portal](../enrollment/media/windows-enroll/auto-enroll-intune.png)

4. Configure **Ámbito de usuario de MDM**. Especifique qué dispositivos de los usuarios deben administrarse mediante Microsoft Intune. Estos dispositivos Windows 10 pueden inscribirse automáticamente para la administración con Microsoft Intune.

   - **Ninguno**: inscripción automática de MDM deshabilitada
   - **Algunos** : seleccione los **Grupos** que pueden inscribir automáticamente sus dispositivos Windows 10
   - **Todos**: todos los usuarios pueden inscribir automáticamente sus dispositivos Windows 10

      > [!IMPORTANT]
      > En el caso de los dispositivos Windows BYOD, el ámbito de usuario de MAM tiene prioridad si los ámbitos de usuario de MAM y MDM (inscripción automática de MDM) están habilitados para todos los usuarios (o los mismos grupos de usuarios). El dispositivo no se inscribirá en MDM y se aplicarán las directivas de Windows Information Protection (WIP), en el caso de que las haya configurado.
      >
      > Si la intención es habilitar la inscripción automática de dispositivos Windows BYOD en una MDM, establezca el ámbito de usuario de MDM en **Todos** (o bien en **Algunos** y especifique un grupo) y el ámbito de usuario de MAM en **Ninguno** (o bien en **Algunos** y especifique un grupo; asegúrese también de que los usuarios no sean miembros de un grupo de destino para los ámbitos de usuario de MDM y MAM).
      >
      >En el caso de los [dispositivos corporativos](../enrollment/enrollment-restrictions-set.md#blocking-personal-windows-devices), el ámbito de usuario de MDM tiene prioridad si los ámbitos de usuario de MDM y MAM están habilitados. El dispositivo se inscribirá de forma automática en la MDM configurada.

   > [!NOTE]
   > El ámbito de usuario de MDM debe establecerse en un grupo de Azure AD que contenga objetos de usuario.

   ![Captura de pantalla de Azure Portal](../enrollment/media/windows-enroll/auto-enroll-scope.png)

5. Utilice los valores predeterminados para las direcciones URL siguientes:
    - **URL de los términos de uso de MDM**
    - **URL de detección de MDM**
    - **URL de cumplimiento de MDM**

6. Seleccione **Guardar**.

De manera predeterminada, la autenticación en dos fases no está habilitada para el servicio. En cambio, se recomienda la autenticación en dos fases al registrar un dispositivo. Para habilitar la autenticación en dos fases, configure un proveedor de autenticación en dos fases en Azure AD, así como las cuentas de usuario para la autenticación multifactor. Vea [Introducción a Servidor Azure Multi-Factor Authentication](/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).