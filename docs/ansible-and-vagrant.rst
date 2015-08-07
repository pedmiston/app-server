Running a one-off django management command on a vagrant server
=======

.. codeblock: bash

  ansible all 
  -i vagrant.inv
  --private-key=.vagrant/machines/default/virtualbox/private_key
  -u vagrant
  -m django_manage
  -a "app_path=/webapps/soundscapes/soundscapes-app/
      virtualenv=/webapps/soundscapes/
      settings=settings.dev
      command=loaddata fixtures=gimlet_shows.yaml"

