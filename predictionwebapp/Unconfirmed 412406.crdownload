import numpy as np
import pickle
import streamlit as st

#loading the save model
model = pickle.load(open('model.pkl', 'rb'))

#creating a function for prediction 

def heart_disease_prediction(input_data):

  #changing the input_data to numpy array
  input_data_as_numpy_array = np.asarray(input_data)
  input_data_reshaped = input_data_as_numpy_array.reshape(1,-1)

  prediction = model.predict(input_data_reshaped)
  print(prediction)

  if (prediction[0]==0):
    return 'The person have no heart diseases'
  else:
    return ' The person have heart diseases'

def main():

  #title.
  st.title('Heart Disease Prediction')

  #getting the input data 

  Age = st.text_input('Enter the age of the person' )
  Sex = st.text_input('Enter the Gender\n 0 for male \n 1 for female')
  ChestPainType = st.text_input('Enter the type of Chest pain\n 0 for NAP \n 1 for ASP \n 2 for ATA \n 3 for TA')
  RestingBP= st.text_input('Enter the BLood Pressure of the person at Rest')
  Cholesterol = st.text_input('Enter the Cholestterol level of the person')
  FastingBS = st.text_input('Enter the Fasting Blood Sugar Level of the person')
  RestingECG =  st.text_input('Enter the ECG\n 0 for ST \n 1 for LSV \n 2 for Normal')
  MaxHR = st.text_input('Enter the Max Heart Rate')
  ExerciseAngina = st.text_input('Enter the Angina value \n 0 for no \n 1 for yes')
  Oldpeak = st.text_input('Enter the old peak value between 0-9 in decimal')
  ST_Slope = st.text_input('Enter the ST_Slope \n 0 for Up\n 1 for Flat \n 2 for Down')

  #codeforprediction 
  diagnosis = ''

  #creating a button for prediction 
  if st.button('Heart Disease Prediction'):
    diagnosis = heart_disease_prediction([Age,Sex,ChestPainType,RestingBP,Cholesterol,FastingBS,RestingECG,MaxHR,ExerciseAngina,Oldpeak,ST_Slope])
  
  st.success(diagnosis)

if __name__=='__main__':
    main()