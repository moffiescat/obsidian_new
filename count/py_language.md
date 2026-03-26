
{'username': remote_admin.get('username'),  
'password': remote_admin.get('password'), 
 'isPrivilege': True, 'type': 'LOCAL', 'services': ['ssh'], 'isAutoChangePass': False}

remote_admin = remote_assets.ssh.Admin()

rdp_assets = remote_asset.rdp.get()

assets = AssetManageUtil(usm1)

assets.update_assets_services(id=asset_id, protocol=rdp_assets.get('protocol'), port=rdp_assets.get('port'))


                                                                               command='''<sendline> passwd\n  
<wait> 2\n  
<sendline> ${oldpassword}\n  
<wait> 2\n  
<sendline> ${newpassword}\n  
<wait> 2\n  
<sendline> ${newpassword}\n  
<wait> 2''',

username= assets_info_1.get('username'), password=assets_info_1.get('password')