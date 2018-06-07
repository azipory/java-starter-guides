FROM ansibleplaybookbundle/apb-base

LABEL "com.redhat.apb.spec"=\

COPY playbooks /opt/apb/actions
COPY roles /opt/ansible/roles
ADD requirements.yml /opt/apb/actions/requirements.yml
RUN ansible-galaxy install -r /opt/apb/actions/requirements.yml -f
RUN chmod -R g=u /opt/{ansible,apb}
USER apb
