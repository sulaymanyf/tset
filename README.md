# tset

 @ApiModelProperty("登录账号")
    @Length(
        max = 50
    )
    @Pattern(
        regexp = "^\\w+([-+.]*\\w+)*@([\\da-z](-[\\da-z])?)+(\\.{1,2}[a-z]+)+$|^\\d{1,20}$",
        groups = {AccountDTO.ILoginGroup.class, AccountDTO.IRegisterGroup.class, AccountDTO.IForgetPassword.class, AccountDTO.ICustomerRegister.class, AccountDTO.IResetPassword.class, AccountDTO.ICheckAccount.class, AccountDTO.IQshRegisterGroup.class, AccountDTO.IBindGroup.class, AccountDTO.IVerificationLoginGroup.class},
        message = "!20015"
    )
    @NotBlank(
        groups = {AccountDTO.ILoginGroup.class, AccountDTO.IRegisterGroup.class, AccountDTO.IForgetPassword.class, AccountDTO.IVerifyForget.class, AccountDTO.ICustomerRegister.class, AccountDTO.IResetPassword.class, AccountDTO.ICheckAccount.class, AccountDTO.IQshRegisterGroup.class, AccountDTO.IBindGroup.class, AccountDTO.IVerificationLoginGroup.class},
        message = "账号不能为空"
    )
    private String loginName;
    @ApiModelProperty("密码")
    @NotBlank(
        groups = {AccountDTO.ILoginGroup.class, AccountDTO.IRegisterGroup.class, AccountDTO.ICustomerRegister.class, AccountDTO.IQshRegisterGroup.class},
        message = "密码不能为空"
    )
    @Pattern(
        regexp = "^(?=.*[a-z])(?=.*[A-Z])(?=.*\\d)[\\s\\S]{8,20}$",
        groups = {AccountDTO.IRegisterGroup.class, AccountDTO.ICustomerRegister.class, AccountDTO.IQshRegisterGroup.class},
        message = "!password.pattern.incorrect"
    )
    private String password;
