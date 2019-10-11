# ChurnPrediction

'
def load_from_google_drive(dir_id):
    files = []
    file_list = drive.ListFile({'q': "'{}' in parents".format(dir_id)}).GetList()
    for f in file_list:
        if f['title'].endswith('pkl'):
            print('  Load file: {}'.format(f['title']))
            f_ = drive.CreateFile({'id': f['id']})
            f_.GetContentFile(f['title'])
            files.append(f['title'])
    return files
  
  
load_from_google_drive('1Fp_7GDH_t7xfnU8aXeKrcBC54_nECOcu')  ### Full dataset
#load_from_google_drive('1haYAgCV-TqTMYIk8N4eGE9H4hY2np5xr')   ### Small dataset
#load_from_google_drive('1CRE27AaxJuX-9Kxtgk2GnmxQt6ECHeJS')   ### Tiny dataset
'
