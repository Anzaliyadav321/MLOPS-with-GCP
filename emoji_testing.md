```python
USER_FLAG = "--user"
```


```python
%pip install $USER_FLAG google-cloud-aiplatform==1.59.0
%pip install $USER_FLAG kfp google-cloud-pipeline-components==0.1.1 --upgrade
%pip uninstall -y shapely pygeos geopandas
%pip install shapely==1.8.5.post1 pygeos==0.12.0 geopandas>=0.12.2
%pip install google-cloud-pipeline-components
```

    Collecting google-cloud-aiplatform==1.59.0
      Downloading google_cloud_aiplatform-1.59.0-py2.py3-none-any.whl.metadata (31 kB)
    Requirement already satisfied: google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (2.29.0)
    Requirement already satisfied: google-auth<3.0.0dev,>=2.14.1 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (2.47.0)
    Requirement already satisfied: proto-plus<2.0.0dev,>=1.22.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (1.27.0)
    Collecting protobuf!=3.20.0,!=3.20.1,!=4.21.0,!=4.21.1,!=4.21.2,!=4.21.3,!=4.21.4,!=4.21.5,<5.0.0dev,>=3.19.5 (from google-cloud-aiplatform==1.59.0)
      Downloading protobuf-4.25.8-cp37-abi3-manylinux2014_x86_64.whl.metadata (541 bytes)
    Requirement already satisfied: packaging>=14.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (25.0)
    Collecting google-cloud-storage<3.0.0dev,>=1.32.0 (from google-cloud-aiplatform==1.59.0)
      Downloading google_cloud_storage-2.19.0-py2.py3-none-any.whl.metadata (9.1 kB)
    Requirement already satisfied: google-cloud-bigquery!=3.20.0,<4.0.0dev,>=1.15.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (3.40.0)
    Requirement already satisfied: google-cloud-resource-manager<3.0.0dev,>=1.3.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (1.16.0)
    Requirement already satisfied: shapely<3.0.0dev in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (2.1.2)
    Requirement already satisfied: pydantic<3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (2.12.5)
    Requirement already satisfied: docstring-parser<1 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform==1.59.0) (0.17.0)
    Requirement already satisfied: googleapis-common-protos<2.0.0,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (1.72.0)
    Requirement already satisfied: requests<3.0.0,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (2.32.5)
    Requirement already satisfied: grpcio<2.0.0,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (1.76.0)
    Requirement already satisfied: grpcio-status<2.0.0,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (1.76.0)
    Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0dev,>=2.14.1->google-cloud-aiplatform==1.59.0) (0.4.2)
    Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0dev,>=2.14.1->google-cloud-aiplatform==1.59.0) (4.9.1)
    Requirement already satisfied: google-cloud-core<3.0.0,>=2.4.1 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery!=3.20.0,<4.0.0dev,>=1.15.0->google-cloud-aiplatform==1.59.0) (2.5.0)
    Requirement already satisfied: google-resumable-media<3.0.0,>=2.0.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery!=3.20.0,<4.0.0dev,>=1.15.0->google-cloud-aiplatform==1.59.0) (2.8.0)
    Requirement already satisfied: python-dateutil<3.0.0,>=2.8.2 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery!=3.20.0,<4.0.0dev,>=1.15.0->google-cloud-aiplatform==1.59.0) (2.9.0.post0)
    Requirement already satisfied: grpc-google-iam-v1<1.0.0,>=0.14.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-resource-manager<3.0.0dev,>=1.3.3->google-cloud-aiplatform==1.59.0) (0.14.3)
    Requirement already satisfied: google-crc32c<2.0dev,>=1.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<3.0.0dev,>=1.32.0->google-cloud-aiplatform==1.59.0) (1.8.0)
    Requirement already satisfied: typing-extensions~=4.12 in /opt/conda/lib/python3.10/site-packages (from grpcio<2.0.0,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (4.15.0)
    INFO: pip is looking at multiple versions of grpcio-status to determine which version is compatible with other requirements. This could take a while.
    Collecting grpcio-status<2.0.0,>=1.33.2 (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0)
      Downloading grpcio_status-1.78.1-py3-none-any.whl.metadata (1.3 kB)
      Downloading grpcio_status-1.78.0-py3-none-any.whl.metadata (1.3 kB)
      Downloading grpcio_status-1.75.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.75.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.74.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.73.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.73.0-py3-none-any.whl.metadata (1.1 kB)
    INFO: pip is still looking at multiple versions of grpcio-status to determine which version is compatible with other requirements. This could take a while.
      Downloading grpcio_status-1.72.2-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.72.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.71.2-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.71.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.70.0-py3-none-any.whl.metadata (1.1 kB)
    INFO: This is taking longer than usual. You might need to provide the dependency resolver with stricter constraints to reduce runtime. See https://pip.pypa.io/warnings/backtracking for guidance. If you want to abort this run, press Ctrl + C.
      Downloading grpcio_status-1.69.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.68.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.68.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.67.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.67.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.66.2-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.66.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.66.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.65.5-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.65.4-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.65.2-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.65.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.64.3-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.64.1-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.64.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.63.2-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.63.0-py3-none-any.whl.metadata (1.1 kB)
      Downloading grpcio_status-1.62.3-py3-none-any.whl.metadata (1.3 kB)
    Requirement already satisfied: annotated-types>=0.6.0 in /opt/conda/lib/python3.10/site-packages (from pydantic<3->google-cloud-aiplatform==1.59.0) (0.7.0)
    Requirement already satisfied: pydantic-core==2.41.5 in /opt/conda/lib/python3.10/site-packages (from pydantic<3->google-cloud-aiplatform==1.59.0) (2.41.5)
    Requirement already satisfied: typing-inspection>=0.4.2 in /opt/conda/lib/python3.10/site-packages (from pydantic<3->google-cloud-aiplatform==1.59.0) (0.4.2)
    Requirement already satisfied: six>=1.5 in /opt/conda/lib/python3.10/site-packages (from python-dateutil<3.0.0,>=2.8.2->google-cloud-bigquery!=3.20.0,<4.0.0dev,>=1.15.0->google-cloud-aiplatform==1.59.0) (1.17.0)
    Requirement already satisfied: charset_normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (3.4.4)
    Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (3.11)
    Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (2.6.3)
    Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform==1.59.0) (2026.1.4)
    Requirement already satisfied: pyasn1>=0.1.3 in /opt/conda/lib/python3.10/site-packages (from rsa<5,>=3.1.4->google-auth<3.0.0dev,>=2.14.1->google-cloud-aiplatform==1.59.0) (0.6.2)
    Requirement already satisfied: numpy>=1.21 in /opt/conda/lib/python3.10/site-packages (from shapely<3.0.0dev->google-cloud-aiplatform==1.59.0) (2.2.6)
    Downloading google_cloud_aiplatform-1.59.0-py2.py3-none-any.whl (5.1 MB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m5.1/5.1 MB[0m [31m41.3 MB/s[0m  [33m0:00:00[0m
    [?25hDownloading google_cloud_storage-2.19.0-py2.py3-none-any.whl (131 kB)
    Downloading grpcio_status-1.62.3-py3-none-any.whl (14 kB)
    Downloading protobuf-4.25.8-cp37-abi3-manylinux2014_x86_64.whl (294 kB)
    Installing collected packages: protobuf, grpcio-status, google-cloud-storage, google-cloud-aiplatform
    [2K   [91m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m[90m╺[0m[90m━━━━━━━━━[0m [32m3/4[0m [google-cloud-aiplatform][33m  WARNING: The script tb-gcp-uploader is installed in '/home/jupyter/.local/bin' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.[0m[33m
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m4/4[0m [google-cloud-aiplatform]
    [1A[2K[31mERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
    gcsfs 2026.1.0 requires google-cloud-storage>=3.7.0, but you have google-cloud-storage 2.19.0 which is incompatible.
    kfp 2.15.2 requires protobuf<7.0,>=6.31.1, but you have protobuf 4.25.8 which is incompatible.
    kfp-pipeline-spec 2.15.2 requires protobuf<7.0,>=6.31.1, but you have protobuf 4.25.8 which is incompatible.
    opentelemetry-proto 1.39.1 requires protobuf<7.0,>=5.0, but you have protobuf 4.25.8 which is incompatible.[0m[31m
    [0mSuccessfully installed google-cloud-aiplatform-1.59.0 google-cloud-storage-2.19.0 grpcio-status-1.62.3 protobuf-4.25.8
    Note: you may need to restart the kernel to use updated packages.
    Requirement already satisfied: kfp in /opt/conda/lib/python3.10/site-packages (2.15.2)
    Collecting google-cloud-pipeline-components==0.1.1
      Downloading google_cloud_pipeline_components-0.1.1-py3-none-any.whl.metadata (1.8 kB)
    Collecting kfp
      Downloading kfp-1.8.23-py3-none-any.whl.metadata (6.1 kB)
    Requirement already satisfied: google-cloud-aiplatform>=1.0.0 in ./.local/lib/python3.10/site-packages (from google-cloud-pipeline-components==0.1.1) (1.59.0)
    Collecting absl-py<2,>=0.9 (from kfp)
      Downloading absl_py-1.4.0-py3-none-any.whl.metadata (2.3 kB)
    Requirement already satisfied: PyYAML~=6.0.1 in /opt/conda/lib/python3.10/site-packages (from kfp) (6.0.3)
    Requirement already satisfied: google-api-core<3,>=2.24.2 in /opt/conda/lib/python3.10/site-packages (from kfp) (2.29.0)
    Requirement already satisfied: google-cloud-storage<4,>=2.2.1 in ./.local/lib/python3.10/site-packages (from kfp) (2.19.0)
    Collecting kubernetes<26,>=8.0.0 (from kfp)
      Downloading kubernetes-25.3.0-py2.py3-none-any.whl.metadata (1.5 kB)
    Collecting google-api-python-client<2,>=1.7.8 (from kfp)
      Downloading google_api_python_client-1.12.11-py2.py3-none-any.whl.metadata (4.2 kB)
    Requirement already satisfied: requests-toolbelt<2,>=0.8.0 in /opt/conda/lib/python3.10/site-packages (from kfp) (1.0.0)
    Collecting cloudpickle<3,>=2.0.0 (from kfp)
      Downloading cloudpickle-2.2.1-py3-none-any.whl.metadata (6.9 kB)
    Collecting kfp-server-api<2.0.0,>=1.1.2 (from kfp)
      Downloading kfp-server-api-1.8.5.tar.gz (58 kB)
      Installing build dependencies ... [?25ldone
    [?25h  Getting requirements to build wheel ... [?25ldone
    [?25h  Preparing metadata (pyproject.toml) ... [?25ldone
    [?25hRequirement already satisfied: jsonschema<5,>=3.0.1 in /opt/conda/lib/python3.10/site-packages (from kfp) (4.26.0)
    Requirement already satisfied: tabulate<1,>=0.8.6 in /opt/conda/lib/python3.10/site-packages (from kfp) (0.9.0)
    Requirement already satisfied: click<9,>=7.1.2 in /opt/conda/lib/python3.10/site-packages (from kfp) (8.3.1)
    Collecting Deprecated<2,>=1.2.7 (from kfp)
      Downloading deprecated-1.3.1-py2.py3-none-any.whl.metadata (5.9 kB)
    Collecting strip-hints<1,>=0.1.8 (from kfp)
      Downloading strip_hints-0.1.13-py3-none-any.whl.metadata (11 kB)
    Requirement already satisfied: docstring-parser<1,>=0.7.3 in /opt/conda/lib/python3.10/site-packages (from kfp) (0.17.0)
    Collecting kfp-pipeline-spec==0.8.0 (from kfp)
      Downloading kfp_pipeline_spec-0.8.0-py3-none-any.whl.metadata (432 bytes)
    Collecting fire<1,>=0.7.0 (from kfp)
      Downloading fire-0.7.1-py3-none-any.whl.metadata (5.8 kB)
    Collecting protobuf<7.0,==6.31.1 (from kfp)
      Downloading protobuf-6.31.1-cp39-abi3-manylinux2014_x86_64.whl.metadata (593 bytes)
    Collecting uritemplate<4,>=3.0.1 (from kfp)
      Downloading uritemplate-3.0.1-py2.py3-none-any.whl.metadata (4.6 kB)
    Requirement already satisfied: urllib3<3.0.0 in /opt/conda/lib/python3.10/site-packages (from kfp) (2.6.3)
    Collecting pydantic<2,>=1.8.2 (from kfp)
      Downloading pydantic-1.10.26-cp310-cp310-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (155 kB)
    Collecting typer<1.0,>=0.3.2 (from kfp)
      Downloading typer-0.24.0-py3-none-any.whl.metadata (16 kB)
    Requirement already satisfied: wrapt<3,>=1.10 in /opt/conda/lib/python3.10/site-packages (from Deprecated<2,>=1.2.7->kfp) (2.0.1)
    Collecting termcolor (from fire<1,>=0.7.0->kfp)
      Downloading termcolor-3.3.0-py3-none-any.whl.metadata (6.5 kB)
    Requirement already satisfied: googleapis-common-protos<2.0.0,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp) (1.72.0)
    Requirement already satisfied: proto-plus<2.0.0,>=1.22.3 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp) (1.27.0)
    Requirement already satisfied: google-auth<3.0.0,>=2.14.1 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp) (2.47.0)
    Requirement already satisfied: requests<3.0.0,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp) (2.32.5)
    Requirement already satisfied: httplib2<1dev,>=0.15.0 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp) (0.31.1)
    Requirement already satisfied: google-auth-httplib2>=0.0.3 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp) (0.3.0)
    Requirement already satisfied: six<2dev,>=1.13.0 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp) (1.17.0)
    Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp) (0.4.2)
    Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp) (4.9.1)
    Requirement already satisfied: google-cloud-core<3.0dev,>=2.3.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp) (2.5.0)
    Requirement already satisfied: google-resumable-media>=2.7.2 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp) (2.8.0)
    Requirement already satisfied: google-crc32c<2.0dev,>=1.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp) (1.8.0)
    Requirement already satisfied: pyparsing<4,>=3.0.4 in /opt/conda/lib/python3.10/site-packages (from httplib2<1dev,>=0.15.0->google-api-python-client<2,>=1.7.8->kfp) (3.3.2)
    Requirement already satisfied: attrs>=22.2.0 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp) (25.4.0)
    Requirement already satisfied: jsonschema-specifications>=2023.03.6 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp) (2025.9.1)
    Requirement already satisfied: referencing>=0.28.4 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp) (0.37.0)
    Requirement already satisfied: rpds-py>=0.25.0 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp) (0.30.0)
    Requirement already satisfied: certifi in /opt/conda/lib/python3.10/site-packages (from kfp-server-api<2.0.0,>=1.1.2->kfp) (2026.1.4)
    Requirement already satisfied: python-dateutil in /opt/conda/lib/python3.10/site-packages (from kfp-server-api<2.0.0,>=1.1.2->kfp) (2.9.0.post0)
    Requirement already satisfied: setuptools>=21.0.0 in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp) (80.9.0)
    Requirement already satisfied: websocket-client!=0.40.0,!=0.41.*,!=0.42.*,>=0.32.0 in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp) (1.9.0)
    Requirement already satisfied: requests-oauthlib in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp) (2.0.0)
    Requirement already satisfied: typing-extensions>=4.2.0 in /opt/conda/lib/python3.10/site-packages (from pydantic<2,>=1.8.2->kfp) (4.15.0)
    Requirement already satisfied: charset_normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core<3,>=2.24.2->kfp) (3.4.4)
    Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core<3,>=2.24.2->kfp) (3.11)
    Requirement already satisfied: pyasn1>=0.1.3 in /opt/conda/lib/python3.10/site-packages (from rsa<5,>=3.1.4->google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp) (0.6.2)
    Requirement already satisfied: wheel in /opt/conda/lib/python3.10/site-packages (from strip-hints<1,>=0.1.8->kfp) (0.45.1)
    Collecting shellingham>=1.3.0 (from typer<1.0,>=0.3.2->kfp)
      Downloading shellingham-1.5.4-py2.py3-none-any.whl.metadata (3.5 kB)
    Requirement already satisfied: rich>=12.3.0 in /opt/conda/lib/python3.10/site-packages (from typer<1.0,>=0.3.2->kfp) (13.9.4)
    Requirement already satisfied: annotated-doc>=0.0.2 in /opt/conda/lib/python3.10/site-packages (from typer<1.0,>=0.3.2->kfp) (0.0.4)
    INFO: pip is looking at multiple versions of google-cloud-aiplatform to determine which version is compatible with other requirements. This could take a while.
    Collecting google-cloud-aiplatform>=1.0.0 (from google-cloud-pipeline-components==0.1.1)
      Downloading google_cloud_aiplatform-1.138.0-py2.py3-none-any.whl.metadata (46 kB)
    Requirement already satisfied: packaging>=14.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (25.0)
    Requirement already satisfied: google-cloud-bigquery!=3.20.0,<4.0.0,>=1.15.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (3.40.0)
    Requirement already satisfied: google-cloud-resource-manager<3.0.0,>=1.3.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (1.16.0)
    Requirement already satisfied: google-genai<2.0.0,>=1.59.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (1.60.0)
    Requirement already satisfied: grpcio<2.0.0,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (1.76.0)
    Requirement already satisfied: grpcio-status<2.0.0,>=1.33.2 in ./.local/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.34.1->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (1.62.3)
    Requirement already satisfied: grpc-google-iam-v1<1.0.0,>=0.14.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-resource-manager<3.0.0,>=1.3.3->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (0.14.3)
    Requirement already satisfied: anyio<5.0.0,>=4.8.0 in /opt/conda/lib/python3.10/site-packages (from google-genai<2.0.0,>=1.59.0->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (4.12.1)
    Requirement already satisfied: httpx<1.0.0,>=0.28.1 in /opt/conda/lib/python3.10/site-packages (from google-genai<2.0.0,>=1.59.0->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (0.28.1)
    INFO: pip is looking at multiple versions of google-genai to determine which version is compatible with other requirements. This could take a while.
    Collecting google-genai<2.0.0,>=1.59.0 (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1)
      Downloading google_genai-1.64.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.63.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.62.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.61.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.59.0-py3-none-any.whl.metadata (53 kB)
    Collecting google-cloud-aiplatform>=1.0.0 (from google-cloud-pipeline-components==0.1.1)
      Downloading google_cloud_aiplatform-1.137.0-py2.py3-none-any.whl.metadata (46 kB)
    INFO: pip is still looking at multiple versions of google-genai to determine which version is compatible with other requirements. This could take a while.
      Downloading google_cloud_aiplatform-1.136.0-py2.py3-none-any.whl.metadata (46 kB)
    INFO: This is taking longer than usual. You might need to provide the dependency resolver with stricter constraints to reduce runtime. See https://pip.pypa.io/warnings/backtracking for guidance. If you want to abort this run, press Ctrl + C.
      Downloading google_cloud_aiplatform-1.135.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.134.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.133.0-py2.py3-none-any.whl.metadata (46 kB)
    Collecting google-genai<2.0.0,>=1.37.0 (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1)
      Downloading google_genai-1.58.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.57.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.56.0-py3-none-any.whl.metadata (53 kB)
      Downloading google_genai-1.55.0-py3-none-any.whl.metadata (47 kB)
      Downloading google_genai-1.54.0-py3-none-any.whl.metadata (47 kB)
      Downloading google_genai-1.53.0-py3-none-any.whl.metadata (47 kB)
      Downloading google_genai-1.52.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.51.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.50.1-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.50.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.49.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.48.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.47.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.46.0-py3-none-any.whl.metadata (46 kB)
      Downloading google_genai-1.45.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.44.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.43.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.42.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.41.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.40.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.39.1-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.39.0-py3-none-any.whl.metadata (45 kB)
      Downloading google_genai-1.38.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.37.0-py3-none-any.whl.metadata (43 kB)
    Collecting google-cloud-aiplatform>=1.0.0 (from google-cloud-pipeline-components==0.1.1)
      Downloading google_cloud_aiplatform-1.132.0-py2.py3-none-any.whl.metadata (46 kB)
    Requirement already satisfied: shapely<3.0.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (2.1.2)
    INFO: pip is still looking at multiple versions of google-cloud-aiplatform to determine which version is compatible with other requirements. This could take a while.
      Downloading google_cloud_aiplatform-1.131.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.130.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.129.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.128.0-py2.py3-none-any.whl.metadata (46 kB)
      Downloading google_cloud_aiplatform-1.127.0-py2.py3-none-any.whl.metadata (46 kB)
    INFO: This is taking longer than usual. You might need to provide the dependency resolver with stricter constraints to reduce runtime. See https://pip.pypa.io/warnings/backtracking for guidance. If you want to abort this run, press Ctrl + C.
      Downloading google_cloud_aiplatform-1.126.1-py2.py3-none-any.whl.metadata (45 kB)
      Downloading google_cloud_aiplatform-1.126.0-py2.py3-none-any.whl.metadata (45 kB)
      Downloading google_cloud_aiplatform-1.125.0-py2.py3-none-any.whl.metadata (45 kB)
      Downloading google_cloud_aiplatform-1.124.0-py2.py3-none-any.whl.metadata (45 kB)
      Downloading google_cloud_aiplatform-1.123.0-py2.py3-none-any.whl.metadata (45 kB)
      Downloading google_cloud_aiplatform-1.122.0-py2.py3-none-any.whl.metadata (44 kB)
      Downloading google_cloud_aiplatform-1.121.0-py2.py3-none-any.whl.metadata (43 kB)
      Downloading google_cloud_aiplatform-1.120.0-py2.py3-none-any.whl.metadata (43 kB)
      Downloading google_cloud_aiplatform-1.119.0-py2.py3-none-any.whl.metadata (43 kB)
      Downloading google_cloud_aiplatform-1.118.0-py2.py3-none-any.whl.metadata (43 kB)
      Downloading google_cloud_aiplatform-1.117.0-py2.py3-none-any.whl.metadata (41 kB)
      Downloading google_cloud_aiplatform-1.116.0-py2.py3-none-any.whl.metadata (41 kB)
      Downloading google_cloud_aiplatform-1.115.0-py2.py3-none-any.whl.metadata (41 kB)
    Collecting google-genai<2.0.0,>=1.0.0 (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1)
      Downloading google_genai-1.36.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.35.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.34.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.33.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.32.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.31.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.30.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.29.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.28.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.27.0-py3-none-any.whl.metadata (43 kB)
      Downloading google_genai-1.26.0-py3-none-any.whl.metadata (42 kB)
      Downloading google_genai-1.25.0-py3-none-any.whl.metadata (41 kB)
      Downloading google_genai-1.24.0-py3-none-any.whl.metadata (40 kB)
      Downloading google_genai-1.23.0-py3-none-any.whl.metadata (38 kB)
      Downloading google_genai-1.22.0-py3-none-any.whl.metadata (37 kB)
      Downloading google_genai-1.21.1-py3-none-any.whl.metadata (37 kB)
      Downloading google_genai-1.21.0-py3-none-any.whl.metadata (37 kB)
      Downloading google_genai-1.20.0-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.19.0-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.18.0-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.17.0-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.16.1-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.15.0-py3-none-any.whl.metadata (35 kB)
      Downloading google_genai-1.14.0-py3-none-any.whl.metadata (33 kB)
      Downloading google_genai-1.13.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.12.1-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.11.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.10.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.9.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.8.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.7.0-py3-none-any.whl.metadata (32 kB)
      Downloading google_genai-1.5.0-py3-none-any.whl.metadata (29 kB)
      Downloading google_genai-1.4.0-py3-none-any.whl.metadata (29 kB)
      Downloading google_genai-1.3.0-py3-none-any.whl.metadata (28 kB)
      Downloading google_genai-1.2.0-py3-none-any.whl.metadata (26 kB)
      Downloading google_genai-1.1.0-py3-none-any.whl.metadata (26 kB)
      Downloading google_genai-1.0.0-py3-none-any.whl.metadata (25 kB)
    Collecting google-cloud-aiplatform>=1.0.0 (from google-cloud-pipeline-components==0.1.1)
      Downloading google_cloud_aiplatform-1.114.0-py2.py3-none-any.whl.metadata (40 kB)
      Downloading google_cloud_aiplatform-1.113.0-py2.py3-none-any.whl.metadata (40 kB)
      Downloading google_cloud_aiplatform-1.112.0-py2.py3-none-any.whl.metadata (40 kB)
      Downloading google_cloud_aiplatform-1.111.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.110.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.109.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.108.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.107.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.106.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.105.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.104.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.103.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.102.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.101.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.100.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.99.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.98.0-py2.py3-none-any.whl.metadata (38 kB)
      Downloading google_cloud_aiplatform-1.97.0-py2.py3-none-any.whl.metadata (36 kB)
      Downloading google_cloud_aiplatform-1.96.0-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.95.1-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.95.0-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.94.0-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.93.1-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.93.0-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.92.0-py2.py3-none-any.whl.metadata (35 kB)
      Downloading google_cloud_aiplatform-1.91.0-py2.py3-none-any.whl.metadata (35 kB)
    Requirement already satisfied: numpy>=1.21 in /opt/conda/lib/python3.10/site-packages (from shapely<3.0.0->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components==0.1.1) (2.2.6)
    Requirement already satisfied: markdown-it-py>=2.2.0 in /opt/conda/lib/python3.10/site-packages (from rich>=12.3.0->typer<1.0,>=0.3.2->kfp) (4.0.0)
    Requirement already satisfied: pygments<3.0.0,>=2.13.0 in /opt/conda/lib/python3.10/site-packages (from rich>=12.3.0->typer<1.0,>=0.3.2->kfp) (2.19.2)
    Requirement already satisfied: mdurl~=0.1 in /opt/conda/lib/python3.10/site-packages (from markdown-it-py>=2.2.0->rich>=12.3.0->typer<1.0,>=0.3.2->kfp) (0.1.2)
    Requirement already satisfied: oauthlib>=3.0.0 in /opt/conda/lib/python3.10/site-packages (from requests-oauthlib->kubernetes<26,>=8.0.0->kfp) (3.3.1)
    Downloading google_cloud_pipeline_components-0.1.1-py3-none-any.whl (17 kB)
    Downloading kfp-1.8.23-py3-none-any.whl (427 kB)
    Downloading protobuf-6.31.1-cp39-abi3-manylinux2014_x86_64.whl (321 kB)
    Downloading kfp_pipeline_spec-0.8.0-py3-none-any.whl (9.6 kB)
    Downloading absl_py-1.4.0-py3-none-any.whl (126 kB)
    Downloading cloudpickle-2.2.1-py3-none-any.whl (25 kB)
    Downloading deprecated-1.3.1-py2.py3-none-any.whl (11 kB)
    Downloading fire-0.7.1-py3-none-any.whl (115 kB)
    Downloading google_api_python_client-1.12.11-py2.py3-none-any.whl (62 kB)
    Downloading kubernetes-25.3.0-py2.py3-none-any.whl (1.4 MB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m1.4/1.4 MB[0m [31m30.6 MB/s[0m  [33m0:00:00[0m
    [?25hDownloading pydantic-1.10.26-cp310-cp310-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (2.9 MB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m2.9/2.9 MB[0m [31m49.3 MB/s[0m  [33m0:00:00[0m
    [?25hDownloading strip_hints-0.1.13-py3-none-any.whl (23 kB)
    Downloading typer-0.24.0-py3-none-any.whl (56 kB)
    Downloading uritemplate-3.0.1-py2.py3-none-any.whl (15 kB)
    Downloading google_cloud_aiplatform-1.91.0-py2.py3-none-any.whl (7.6 MB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m7.6/7.6 MB[0m [31m34.8 MB/s[0m  [33m0:00:00[0m eta [36m0:00:01[0m
    [?25hDownloading shellingham-1.5.4-py2.py3-none-any.whl (9.8 kB)
    Downloading termcolor-3.3.0-py3-none-any.whl (7.7 kB)
    Building wheels for collected packages: kfp-server-api
      Building wheel for kfp-server-api (pyproject.toml) ... [?25ldone
    [?25h  Created wheel for kfp-server-api: filename=kfp_server_api-1.8.5-py3-none-any.whl size=99777 sha256=0b809b7177a445cc807ed777fe04afd8d9e4ebdc77c5ede18934f1aa073e49bf
      Stored in directory: /home/jupyter/.cache/pip/wheels/c5/97/d5/e8a0f596dc85f5cfe383c800fbf3e29a99853bb54e01f26fca
    Successfully built kfp-server-api
    Installing collected packages: uritemplate, termcolor, strip-hints, shellingham, pydantic, protobuf, Deprecated, cloudpickle, absl-py, kfp-server-api, kfp-pipeline-spec, fire, typer, kubernetes, google-api-python-client, kfp, google-cloud-aiplatform, google-cloud-pipeline-components
    [?25l[33m  WARNING: The script strip-hints is installed in '/home/jupyter/.local/bin' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.[0m[33m
    [2K  Attempting uninstall: protobuf90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m 4/18[0m [pydantic]
    [2K    Found existing installation: protobuf 4.25.8━━━━━━━━━━━━━━[0m [32m 4/18[0m [pydantic]
    [2K    Uninstalling protobuf-4.25.8:━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m 4/18[0m [pydantic]
    [2K      Successfully uninstalled protobuf-4.25.8━━━━━━━━━━━━━━━━[0m [32m 4/18[0m [pydantic]
    [2K   [91m━━━━━━━━━━━━━━━━━━━━━━━━[0m[90m╺[0m[90m━━━━━━━━━━━━━━━[0m [32m11/18[0m [fire][33m  WARNING: The script typer is installed in '/home/jupyter/.local/bin' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.[0m[33m
    [2K   [91m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m[90m╺[0m[90m━━━━━━[0m [32m15/18[0m [kfp][33m  WARNING: The scripts dsl-compile, dsl-compile-v2 and kfp are installed in '/home/jupyter/.local/bin' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.[0m[33m
    [2K  Attempting uninstall: google-cloud-aiplatform
    [2K    Found existing installation: google-cloud-aiplatform 1.59.0[0m [32m15/18[0m [kfp]
    [2K    Uninstalling google-cloud-aiplatform-1.59.0:[91m╸[0m[90m━━━━[0m [32m16/18[0m [google-cloud-aiplatform]
    [2K      Successfully uninstalled google-cloud-aiplatform-1.59.0━[0m [32m16/18[0m [google-cloud-aiplatform]
    [2K   [91m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m[91m╸[0m[90m━━━━[0m [32m16/18[0m [google-cloud-aiplatform][33m  WARNING: The script tb-gcp-uploader is installed in '/home/jupyter/.local/bin' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.[0m[33m
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m18/18[0m [google-cloud-pipeline-components]d-aiplatform]
    [1A[2K[31mERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
    fastapi 0.128.0 requires pydantic>=2.7.0, but you have pydantic 1.10.26 which is incompatible.
    google-genai 1.60.0 requires pydantic<3.0.0,>=2.9.0, but you have pydantic 1.10.26 which is incompatible.
    ydata-profiling 4.18.1 requires pydantic<3,>=2, but you have pydantic 1.10.26 which is incompatible.[0m[31m
    [0mSuccessfully installed Deprecated-1.3.1 absl-py-1.4.0 cloudpickle-2.2.1 fire-0.7.1 google-api-python-client-1.12.11 google-cloud-aiplatform-1.91.0 google-cloud-pipeline-components-0.1.1 kfp-1.8.23 kfp-pipeline-spec-0.8.0 kfp-server-api-1.8.5 kubernetes-25.3.0 protobuf-6.31.1 pydantic-1.10.26 shellingham-1.5.4 strip-hints-0.1.13 termcolor-3.3.0 typer-0.24.0 uritemplate-3.0.1
    Note: you may need to restart the kernel to use updated packages.
    Found existing installation: shapely 2.1.2
    Uninstalling shapely-2.1.2:
      Successfully uninstalled shapely-2.1.2
    [33mWARNING: Skipping pygeos as it is not installed.[0m[33m
    [0mFound existing installation: geopandas 1.1.2
    Uninstalling geopandas-1.1.2:
      Successfully uninstalled geopandas-1.1.2
    Note: you may need to restart the kernel to use updated packages.
    Note: you may need to restart the kernel to use updated packages.
    Requirement already satisfied: google-cloud-pipeline-components in ./.local/lib/python3.10/site-packages (0.1.1)
    Requirement already satisfied: kfp<2.0.0,>=1.4.0 in ./.local/lib/python3.10/site-packages (from google-cloud-pipeline-components) (1.8.23)
    Requirement already satisfied: google-cloud-aiplatform>=1.0.0 in ./.local/lib/python3.10/site-packages (from google-cloud-pipeline-components) (1.91.0)
    Requirement already satisfied: absl-py<2,>=0.9 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.4.0)
    Requirement already satisfied: PyYAML~=6.0.1 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (6.0.3)
    Requirement already satisfied: google-api-core<3,>=2.24.2 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.29.0)
    Requirement already satisfied: google-cloud-storage<4,>=2.2.1 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.19.0)
    Requirement already satisfied: kubernetes<26,>=8.0.0 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (25.3.0)
    Requirement already satisfied: google-api-python-client<2,>=1.7.8 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.12.11)
    Requirement already satisfied: requests-toolbelt<2,>=0.8.0 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.0.0)
    Requirement already satisfied: cloudpickle<3,>=2.0.0 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.2.1)
    Requirement already satisfied: kfp-server-api<2.0.0,>=1.1.2 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.8.5)
    Requirement already satisfied: jsonschema<5,>=3.0.1 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (4.26.0)
    Requirement already satisfied: tabulate<1,>=0.8.6 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.9.0)
    Requirement already satisfied: click<9,>=7.1.2 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (8.3.1)
    Requirement already satisfied: Deprecated<2,>=1.2.7 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.3.1)
    Requirement already satisfied: strip-hints<1,>=0.1.8 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.1.13)
    Requirement already satisfied: docstring-parser<1,>=0.7.3 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.17.0)
    Requirement already satisfied: kfp-pipeline-spec==0.8.0 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.8.0)
    Requirement already satisfied: fire<1,>=0.7.0 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.7.1)
    Requirement already satisfied: protobuf<7.0,==6.31.1 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (6.31.1)
    Requirement already satisfied: uritemplate<4,>=3.0.1 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.0.1)
    Requirement already satisfied: urllib3<3.0.0 in /opt/conda/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.6.3)
    Requirement already satisfied: pydantic<2,>=1.8.2 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.10.26)
    Requirement already satisfied: typer<1.0,>=0.3.2 in ./.local/lib/python3.10/site-packages (from kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.24.0)
    Requirement already satisfied: wrapt<3,>=1.10 in /opt/conda/lib/python3.10/site-packages (from Deprecated<2,>=1.2.7->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.0.1)
    Requirement already satisfied: termcolor in ./.local/lib/python3.10/site-packages (from fire<1,>=0.7.0->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.3.0)
    Requirement already satisfied: googleapis-common-protos<2.0.0,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.72.0)
    Requirement already satisfied: proto-plus<2.0.0,>=1.22.3 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.27.0)
    Requirement already satisfied: google-auth<3.0.0,>=2.14.1 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.47.0)
    Requirement already satisfied: requests<3.0.0,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.32.5)
    Requirement already satisfied: httplib2<1dev,>=0.15.0 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.31.1)
    Requirement already satisfied: google-auth-httplib2>=0.0.3 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.3.0)
    Requirement already satisfied: six<2dev,>=1.13.0 in /opt/conda/lib/python3.10/site-packages (from google-api-python-client<2,>=1.7.8->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.17.0)
    Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.4.2)
    Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (4.9.1)
    Requirement already satisfied: google-cloud-core<3.0dev,>=2.3.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.5.0)
    Requirement already satisfied: google-resumable-media>=2.7.2 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.8.0)
    Requirement already satisfied: google-crc32c<2.0dev,>=1.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<4,>=2.2.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.8.0)
    Requirement already satisfied: pyparsing<4,>=3.0.4 in /opt/conda/lib/python3.10/site-packages (from httplib2<1dev,>=0.15.0->google-api-python-client<2,>=1.7.8->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.3.2)
    Requirement already satisfied: attrs>=22.2.0 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (25.4.0)
    Requirement already satisfied: jsonschema-specifications>=2023.03.6 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2025.9.1)
    Requirement already satisfied: referencing>=0.28.4 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.37.0)
    Requirement already satisfied: rpds-py>=0.25.0 in /opt/conda/lib/python3.10/site-packages (from jsonschema<5,>=3.0.1->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.30.0)
    Requirement already satisfied: certifi in /opt/conda/lib/python3.10/site-packages (from kfp-server-api<2.0.0,>=1.1.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2026.1.4)
    Requirement already satisfied: python-dateutil in /opt/conda/lib/python3.10/site-packages (from kfp-server-api<2.0.0,>=1.1.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.9.0.post0)
    Requirement already satisfied: setuptools>=21.0.0 in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (80.9.0)
    Requirement already satisfied: websocket-client!=0.40.0,!=0.41.*,!=0.42.*,>=0.32.0 in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.9.0)
    Requirement already satisfied: requests-oauthlib in /opt/conda/lib/python3.10/site-packages (from kubernetes<26,>=8.0.0->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.0.0)
    Requirement already satisfied: typing-extensions>=4.2.0 in /opt/conda/lib/python3.10/site-packages (from pydantic<2,>=1.8.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (4.15.0)
    Requirement already satisfied: charset_normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.4.4)
    Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0,>=2.18.0->google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.11)
    Requirement already satisfied: pyasn1>=0.1.3 in /opt/conda/lib/python3.10/site-packages (from rsa<5,>=3.1.4->google-auth<3.0.0,>=2.14.1->google-api-core<3,>=2.24.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.6.2)
    Requirement already satisfied: wheel in /opt/conda/lib/python3.10/site-packages (from strip-hints<1,>=0.1.8->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.45.1)
    Requirement already satisfied: shellingham>=1.3.0 in ./.local/lib/python3.10/site-packages (from typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (1.5.4)
    Requirement already satisfied: rich>=12.3.0 in /opt/conda/lib/python3.10/site-packages (from typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (13.9.4)
    Requirement already satisfied: annotated-doc>=0.0.2 in /opt/conda/lib/python3.10/site-packages (from typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.0.4)
    Requirement already satisfied: packaging>=14.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (25.0)
    Requirement already satisfied: google-cloud-bigquery!=3.20.0,<4.0.0,>=1.15.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (3.40.0)
    Requirement already satisfied: google-cloud-resource-manager<3.0.0,>=1.3.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (1.16.0)
    Requirement already satisfied: shapely<3.0.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (1.8.5.post1)
    Requirement already satisfied: grpcio<2.0.0,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0,>=1.34.1->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (1.76.0)
    Requirement already satisfied: grpcio-status<2.0.0,>=1.33.2 in ./.local/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0,>=1.34.1->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (1.62.3)
    Requirement already satisfied: grpc-google-iam-v1<1.0.0,>=0.14.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-resource-manager<3.0.0,>=1.3.3->google-cloud-aiplatform>=1.0.0->google-cloud-pipeline-components) (0.14.3)
    Requirement already satisfied: markdown-it-py>=2.2.0 in /opt/conda/lib/python3.10/site-packages (from rich>=12.3.0->typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (4.0.0)
    Requirement already satisfied: pygments<3.0.0,>=2.13.0 in /opt/conda/lib/python3.10/site-packages (from rich>=12.3.0->typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (2.19.2)
    Requirement already satisfied: mdurl~=0.1 in /opt/conda/lib/python3.10/site-packages (from markdown-it-py>=2.2.0->rich>=12.3.0->typer<1.0,>=0.3.2->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (0.1.2)
    Requirement already satisfied: oauthlib>=3.0.0 in /opt/conda/lib/python3.10/site-packages (from requests-oauthlib->kubernetes<26,>=8.0.0->kfp<2.0.0,>=1.4.0->google-cloud-pipeline-components) (3.3.1)
    Note: you may need to restart the kernel to use updated packages.



```python
#Step 2: Set your project ID and bucket

```


```python
import os

if not os.getenv("IS_TESTING"):
    # Automatically restart kernel after installs
    import IPython

    app = IPython.Application.instance()
    app.kernel.do_shutdown(True)
```


```python
!python3 -c "import kfp; print('KFP SDK version: {}'.format(kfp.__version__))"
!python3 -c "import google_cloud_pipeline_components; print('google_cloud_pipeline_components version: {}'.format(google_cloud_pipeline_components.__version__))"
```

    KFP SDK version: 1.8.23
    google_cloud_pipeline_components version: 0.1.1



```python
import os
PROJECT_ID = ""

# Get your Google Cloud project ID from gcloud
if not os.getenv("IS_TESTING"):
    shell_output=!gcloud config list --format 'value(core.project)' 2>/dev/null
    PROJECT_ID = shell_output[0]
    print("Project ID: ", PROJECT_ID)
```

    Project ID:  qwiklabs-gcp-02-32baa808c3a8



```python
BUCKET_NAME="gs://" + PROJECT_ID + "-labconfig-bucket"
```


```python
#Step 3: Import libraries
```


```python
from typing import NamedTuple

import kfp
from kfp import dsl
from kfp.v2 import compiler
from kfp.v2.dsl import (Artifact, Dataset, Input, InputPath, Model, Output,
                        OutputPath, ClassificationMetrics, Metrics, component)
from kfp.v2.google.client import AIPlatformClient

from google.cloud import aiplatform
from google_cloud_pipeline_components import aiplatform as gcc_aip
```

    /home/jupyter/.local/lib/python3.10/site-packages/kfp/v2/google/client/client.py:18: UserWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html. The pkg_resources package is slated for removal as early as 2025-11-30. Refrain from using this package or pin to Setuptools<81.
      import pkg_resources
    /opt/conda/lib/python3.10/site-packages/google/api_core/_python_version_support.py:275: FutureWarning: You are using a Python version (3.10.19) which Google will stop supporting in new releases of google.cloud.resourcemanager_v3 once it reaches its end of life (2026-10-04). Please upgrade to the latest Python version, or at least Python 3.11, to continue receiving updates for google.cloud.resourcemanager_v3 past that date.
      warnings.warn(message, FutureWarning)



```python
#Step 4: Define constants
```


```python
PATH=%env PATH
%env PATH={PATH}:/home/jupyter/.local/bin
REGION="us-central1"


PIPELINE_ROOT = f"{BUCKET_NAME}/pipeline_root/"
PIPELINE_ROOT
```

    env: PATH=/usr/local/cuda/bin:/opt/conda/bin:/opt/conda/condabin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/usr/local/sbin:/home/jupyter/.local/bin





    'gs://qwiklabs-gcp-02-32baa808c3a8-labconfig-bucket/pipeline_root/'




```python
#Task 3. Creating your first pipeline
```


```python
#Step 1: Create a Python function based component
```


```python
@component(base_image="python:3.12", output_component_file="first-component.yaml")
def product_name(text: str) -> str:
    return text
```


```python
product_name_component = kfp.components.load_component_from_file('./first-component.yaml')
```


```python
#Step 2: Create two additional components
```


```python
@component(base_image="python:3.12", output_component_file="second-component.yaml", packages_to_install=["emoji"])
def emoji(
    text: str,
) -> NamedTuple(
    "Outputs",
    [
        ("emoji_text", str),  # Return parameters
        ("emoji", str),
    ],
):
    import emoji

    emoji_text = text
    emoji_str = emoji.emojize(':' + emoji_text + ':', language='alias')
    print("output one: {}; output_two: {}".format(emoji_text, emoji_str))
    return (emoji_text, emoji_str)
```


```python
@component(base_image="python:3.12", output_component_file="third-component.yaml")
def build_sentence(
    product: str,
    emoji: str,
    emojitext: str
) -> str:
    print("We completed the pipeline, hooray!")
    end_str = product + " is "
    if len(emoji) > 0:
        end_str += emoji
    else:
        end_str += emojitext
    return(end_str)
```


```python
#Step 3: Putting the components together into a pipeline
```


```python
@dsl.pipeline(
    name="hello-world",
    description="An intro pipeline",
    pipeline_root=PIPELINE_ROOT,
)

# You can change the `text` and `emoji_str` parameters here to update the pipeline output
def intro_pipeline(text: str = "Vertex AI Pipelines", emoji_str: str = "sparkles"):
    product_task = product_name(text)
    emoji_task = emoji(emoji_str)
    consumer_task = build_sentence(
        product_task.output,
        emoji_task.outputs["emoji"],
        emoji_task.outputs["emoji_text"],
    )
```


```python
#compile and run the pipeline
compiler.Compiler().compile(
    pipeline_func=intro_pipeline, package_path="intro_pipeline_job.json"
)
```

    /home/jupyter/.local/lib/python3.10/site-packages/kfp/v2/compiler/compiler.py:1290: FutureWarning: APIs imported from the v1 namespace (e.g. kfp.dsl, kfp.components, etc) will not be supported by the v2 compiler since v2.0.0
      warnings.warn(



```python
#instantiate api_client
api_client = AIPlatformClient(
    project_id=PROJECT_ID,
    region=REGION,
)
```


```python
#run the pipeline
response = api_client.create_run_from_job_spec(
    job_spec_path="intro_pipeline_job.json",
    # pipeline_root=PIPELINE_ROOT  # this argument is necessary if you did not specify PIPELINE_ROOT as part of the pipeline definition.
)
```

    httplib2 transport does not support per-request timeout. Set the timeout when constructing the httplib2.Http instance.
    httplib2 transport does not support per-request timeout. Set the timeout when constructing the httplib2.Http instance.



See the Pipeline job <a href="https://console.cloud.google.com/vertex-ai/locations/us-central1/pipelines/runs/hello-world-20260221105705?project=qwiklabs-gcp-02-32baa808c3a8" target="_blank" >here</a>.



```python
#Task 4. Creating an end-to-end ML pipeline
#Step 1: A custom component for model evaluation
@component(
    base_image="gcr.io/deeplearning-platform-release/tf2-cpu.2-3:latest",
    output_component_file="tables_eval_component.yaml", # Optional: you can use this to load the component later
    packages_to_install=["google-cloud-aiplatform"],
)
def classif_model_eval_metrics(
    project: str,
    location: str,  # "region",
    api_endpoint: str,  # "region-aiplatform.googleapis.com",
    thresholds_dict_str: str,
    model: Input[Model],
    metrics: Output[Metrics],
    metricsc: Output[ClassificationMetrics],
) -> NamedTuple("Outputs", [("dep_decision", str)]):  # Return parameter.

    """This function renders evaluation metrics for an AutoML Tabular classification model.
    It retrieves the classification model evaluation generated by the AutoML Tabular training
    process, does some parsing, and uses that info to render the ROC curve and confusion matrix
    for the model. It also uses given metrics threshold information and compares that to the
    evaluation results to determine whether the model is sufficiently accurate to deploy.
    """
    import json
    import logging

    from google.cloud import aiplatform

    # Fetch model eval info
    def get_eval_info(client, model_name):
        from google.protobuf.json_format import MessageToDict

        response = client.list_model_evaluations(parent=model_name)
        metrics_list = []
        metrics_string_list = []
        for evaluation in response:
            print("model_evaluation")
            print(" name:", evaluation.name)
            print(" metrics_schema_uri:", evaluation.metrics_schema_uri)
            metrics = MessageToDict(evaluation._pb.metrics)
            for metric in metrics.keys():
                logging.info("metric: %s, value: %s", metric, metrics[metric])
            metrics_str = json.dumps(metrics)
            metrics_list.append(metrics)
            metrics_string_list.append(metrics_str)

        return (
            evaluation.name,
            metrics_list,
            metrics_string_list,
        )

    # Use the given metrics threshold(s) to determine whether the model is
    # accurate enough to deploy.
    def classification_thresholds_check(metrics_dict, thresholds_dict):
        for k, v in thresholds_dict.items():
            logging.info("k {}, v {}".format(k, v))
            if k in ["auRoc", "auPrc"]:  # higher is better
                if metrics_dict[k] < v:  # if under threshold, don't deploy
                    logging.info(
                        "{} < {}; returning False".format(metrics_dict[k], v)
                    )
                    return False
        logging.info("threshold checks passed.")
        return True

    def log_metrics(metrics_list, metricsc):
        test_confusion_matrix = metrics_list[0]["confusionMatrix"]
        logging.info("rows: %s", test_confusion_matrix["rows"])

        # log the ROC curve
        fpr = []
        tpr = []
        thresholds = []
        for item in metrics_list[0]["confidenceMetrics"]:
            fpr.append(item.get("falsePositiveRate", 0.0))
            tpr.append(item.get("recall", 0.0))
            thresholds.append(item.get("confidenceThreshold", 0.0))
        print(f"fpr: {fpr}")
        print(f"tpr: {tpr}")
        print(f"thresholds: {thresholds}")
        metricsc.log_roc_curve(fpr, tpr, thresholds)

        # log the confusion matrix
        annotations = []
        for item in test_confusion_matrix["annotationSpecs"]:
            annotations.append(item["displayName"])
        logging.info("confusion matrix annotations: %s", annotations)
        metricsc.log_confusion_matrix(
            annotations,
            test_confusion_matrix["rows"],
        )

        # log textual metrics info as well
        for metric in metrics_list[0].keys():
            if metric != "confidenceMetrics":
                val_string = json.dumps(metrics_list[0][metric])
                metrics.log_metric(metric, val_string)
        # metrics.metadata["model_type"] = "AutoML Tabular classification"

    logging.getLogger().setLevel(logging.INFO)
    aiplatform.init(project=project)
    # extract the model resource name from the input Model Artifact
    model_resource_path = model.uri.replace("aiplatform://v1/", "")
    logging.info("model path: %s", model_resource_path)

    client_options = {"api_endpoint": api_endpoint}
    # Initialize client that will be used to create and send requests.
    client = aiplatform.gapic.ModelServiceClient(client_options=client_options)
    eval_name, metrics_list, metrics_str_list = get_eval_info(
        client, model_resource_path
    )
    logging.info("got evaluation name: %s", eval_name)
    logging.info("got metrics list: %s", metrics_list)
    log_metrics(metrics_list, metricsc)

    thresholds_dict = json.loads(thresholds_dict_str)
    deploy = classification_thresholds_check(metrics_list[0], thresholds_dict)
    if deploy:
        dep_decision = "true"
    else:
        dep_decision = "false"
    logging.info("deployment decision is %s", dep_decision)

    return (dep_decision,)
```


```python
#Step 2: Adding Google Cloud pre-built components
#1.First, define the display name for your pipeline run using a timestamp:

import time
DISPLAY_NAME = 'automl-beans{}'.format(str(int(time.time())))
print(DISPLAY_NAME)
```

    automl-beans1771671798



```python
#2.Then copy the following into a new notebook cell:
@kfp.dsl.pipeline(name="automl-tab-beans-training-v2",
                  pipeline_root=PIPELINE_ROOT)
def pipeline(
    bq_source: str = "bq://aju-dev-demos.beans.beans1",
    display_name: str = DISPLAY_NAME,
    project: str = PROJECT_ID,
    gcp_region: str = "us-central1",
    api_endpoint: str = "us-central1-aiplatform.googleapis.com",
    thresholds_dict_str: str = '{"auRoc": 0.95}',
):
    dataset_create_op = gcc_aip.TabularDatasetCreateOp(
        project=project, display_name=display_name, bq_source=bq_source
    )

    training_op = gcc_aip.AutoMLTabularTrainingJobRunOp(
        project=project,
        display_name=display_name,
        optimization_prediction_type="classification",
        budget_milli_node_hours=1000,
        column_transformations=[
            {"numeric": {"column_name": "Area"}},
            {"numeric": {"column_name": "Perimeter"}},
            {"numeric": {"column_name": "MajorAxisLength"}},
            {"numeric": {"column_name": "MinorAxisLength"}},
            {"numeric": {"column_name": "AspectRation"}},
            {"numeric": {"column_name": "Eccentricity"}},
            {"numeric": {"column_name": "ConvexArea"}},
            {"numeric": {"column_name": "EquivDiameter"}},
            {"numeric": {"column_name": "Extent"}},
            {"numeric": {"column_name": "Solidity"}},
            {"numeric": {"column_name": "roundness"}},
            {"numeric": {"column_name": "Compactness"}},
            {"numeric": {"column_name": "ShapeFactor1"}},
            {"numeric": {"column_name": "ShapeFactor2"}},
            {"numeric": {"column_name": "ShapeFactor3"}},
            {"numeric": {"column_name": "ShapeFactor4"}},
            {"categorical": {"column_name": "Class"}},
        ],
        dataset=dataset_create_op.outputs["dataset"],
        target_column="Class",
    )
    model_eval_task = classif_model_eval_metrics(
        project,
        gcp_region,
        api_endpoint,
        thresholds_dict_str,
        training_op.outputs["model"],
    )

    with dsl.Condition(
        model_eval_task.outputs["dep_decision"] == "true",
        name="deploy_decision",
    ):

        deploy_op = gcc_aip.ModelDeployOp(  # noqa: F841
            model=training_op.outputs["model"],
            project=project,
            machine_type="e2-standard-4",
        )
```


```python
#Step 3: Compile and run the end-to-end ML pipeline
#1.With the full pipeline defined, it's time to compile it:
compiler.Compiler().compile(
    pipeline_func=pipeline, package_path="tab_classif_pipeline.json"
)
```


```python
#2.Next, kick off a pipeline run:
response = api_client.create_run_from_job_spec(
    "tab_classif_pipeline.json", pipeline_root=PIPELINE_ROOT,
    parameter_values={"project": PROJECT_ID,"display_name": DISPLAY_NAME}
)
```


See the Pipeline job <a href="https://console.cloud.google.com/vertex-ai/locations/us-central1/pipelines/runs/automl-tab-beans-training-v2-20260221110534?project=qwiklabs-gcp-02-32baa808c3a8" target="_blank" >here</a>.



```python
#Step 4: Comparing metrics across pipeline runs (Optional)
pipeline_df = aiplatform.get_pipeline_df(pipeline="automl-tab-beans-training-v2")
small_pipeline_df = pipeline_df.head(2)
small_pipeline_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pipeline_name</th>
      <th>run_name</th>
      <th>param.input:display_name</th>
      <th>param.input:api_endpoint</th>
      <th>param.input:thresholds_dict_str</th>
      <th>param.input:bq_source</th>
      <th>param.input:gcp_region</th>
      <th>param.vmlmd_lineage_integration</th>
      <th>param.input:project</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>automl-tab-beans-training-v2</td>
      <td>automl-tab-beans-training-v2-20260221110534</td>
      <td>automl-beans1771671798</td>
      <td>us-central1-aiplatform.googleapis.com</td>
      <td>{"auRoc": 0.95}</td>
      <td>bq://aju-dev-demos.beans.beans1</td>
      <td>us-central1</td>
      <td>{'pipeline_run_component': {'project_id': 'qwi...</td>
      <td>qwiklabs-gcp-02-32baa808c3a8</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
